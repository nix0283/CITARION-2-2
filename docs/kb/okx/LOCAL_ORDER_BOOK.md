# OKX Local Order Book Management

Maintaining a local order book via WebSocket is essential for high-frequency trading strategies that require real-time market depth data. OKX provides order book WebSocket streams with snapshot and update modes.

## How Order Book WebSocket Works

OKX's order book stream follows this flow:

1. **Subscribe** to `books`, `books5`, `books50-l2-tbt`, or `books-l2-tbt` channel
2. **Receive snapshot** - First message contains the full order book state
3. **Receive updates** - Subsequent messages contain only changes
4. **Apply updates** - Update your local order book with each update message
5. **Validate checksum** - Use CRC32 checksum to verify order book integrity

## Order Book Channel Comparison

| Channel | Depth | Update Mode | Update Speed | Use Case |
|---------|-------|-------------|--------------|----------|
| `books5` | 5 levels | Snapshot | 100ms | Quick price display |
| `books50-l2-tbt` | 50 levels | Snapshot + Update | Tick-by-tick | Standard trading |
| `books-l2-tbt` | Full depth | Snapshot + Update | Tick-by-tick | Market making |
| `books` | 400 levels | Snapshot + Update | 100ms | Full depth analysis |

## WebSocket URLs

| Environment | URL |
|-------------|-----|
| Public WebSocket | `wss://ws.okx.com:8443/ws/v5/public` |
| Private WebSocket | `wss://ws.okx.com:8443/ws/v5/private` |
| Business WebSocket | `wss://ws.okx.com:8443/ws/v5/business` |

## Local Order Book Implementation

```typescript
import WebSocket from 'ws';
import crc32 from 'crc-32';

interface OrderBookLevel {
  price: number;
  size: number;
}

interface OkxOrderBookMessage {
  event?: string;
  arg?: {
    channel: string;
    instId: string;
  };
  action?: 'snapshot' | 'update';
  data?: [{
    asks: [string, string, string, string?][];  // [price, size, liquidatedOrders, numOrders?]
    bids: [string, string, string, string?][];
    ts: string;
    checksum: number;
    prevSeqId?: number;
    seqId: number;
  }];
}

class OkxLocalOrderBook {
  private ws: WebSocket | null = null;
  private bids: Map<number, number> = new Map();
  private asks: Map<number, number> = new Map();
  private lastSeqId: number = 0;
  private lastChecksum: number = 0;
  private symbol: string;
  private channel: string;
  private isSnapshotReceived: boolean = false;
  private updateBuffer: OkxOrderBookMessage[] = [];
  private onUpdateCallback: (() => void) | null = null;
  
  // Ping/pong management
  private pingInterval: NodeJS.Timeout | null = null;
  private lastPongTime: number = Date.now();

  constructor(symbol: string, channel: string = 'books50-l2-tbt') {
    this.symbol = symbol;
    this.channel = channel;
  }

  async connect(): Promise<void> {
    return new Promise((resolve, reject) => {
      const url = 'wss://ws.okx.com:8443/ws/v5/public';
      this.ws = new WebSocket(url);

      this.ws.on('open', () => {
        console.log(`[OKX] Connected to orderbook stream for ${this.symbol}`);
        
        // Subscribe to orderbook
        this.ws!.send(JSON.stringify({
          op: 'subscribe',
          args: [{
            channel: this.channel,
            instId: this.symbol
          }]
        }));
        
        // Start ping/pong
        this.startPing();
        
        resolve();
      });

      this.ws.on('message', (data: Buffer) => {
        try {
          // Handle pong
          if (data.toString() === 'pong') {
            this.lastPongTime = Date.now();
            return;
          }
          
          const message = JSON.parse(data.toString()) as OkxOrderBookMessage;
          
          // Skip subscription confirmation
          if (message.event === 'subscribe') {
            console.log(`[OKX] Subscribed to ${message.arg?.channel}`);
            return;
          }
          
          if (message.data && message.arg?.channel?.startsWith('books')) {
            this.handleMessage(message);
          }
        } catch (error) {
          console.error('[OKX] Error parsing message:', error);
        }
      });

      this.ws.on('error', (error) => {
        console.error('[OKX] WebSocket error:', error);
        reject(error);
      });

      this.ws.on('close', () => {
        console.log('[OKX] WebSocket connection closed');
        this.stopPing();
        this.handleReconnect();
      });
    });
  }

  private startPing(): void {
    this.pingInterval = setInterval(() => {
      if (this.ws?.readyState === WebSocket.OPEN) {
        // Check for stale connection
        if (Date.now() - this.lastPongTime > 30000) {
          console.warn('[OKX] Connection stale, reconnecting...');
          this.ws.close();
          return;
        }
        this.ws.send('ping');
      }
    }, 25000);
  }

  private stopPing(): void {
    if (this.pingInterval) {
      clearInterval(this.pingInterval);
      this.pingInterval = null;
    }
  }

  private handleMessage(message: OkxOrderBookMessage): void {
    const { action, data } = message;
    if (!data || data.length === 0) return;
    
    const bookData = data[0];
    
    if (action === 'snapshot') {
      this.processSnapshot(bookData);
      this.isSnapshotReceived = true;
      
      // Process buffered updates
      this.processBufferedUpdates();
    } else if (action === 'update') {
      if (!this.isSnapshotReceived) {
        // Buffer until snapshot received
        this.updateBuffer.push(message);
        return;
      }
      
      // Validate sequence
      if (bookData.prevSeqId && bookData.prevSeqId !== this.lastSeqId) {
        console.warn(`[OKX] Sequence gap: expected ${this.lastSeqId}, got ${bookData.prevSeqId}`);
        this.resubscribe();
        return;
      }
      
      this.processUpdate(bookData);
    }
    
    // Validate checksum
    if (!this.validateChecksum(bookData.checksum)) {
      console.warn('[OKX] Checksum mismatch, resubscribing');
      this.resubscribe();
      return;
    }
    
    if (this.onUpdateCallback) {
      this.onUpdateCallback();
    }
  }

  private processSnapshot(data: any): void {
    this.bids.clear();
    this.asks.clear();
    
    // Process bids (sorted descending by price)
    for (const [price, size] of data.bids) {
      const p = parseFloat(price);
      const s = parseFloat(size);
      if (s > 0) {
        this.bids.set(p, s);
      }
    }
    
    // Process asks (sorted ascending by price)
    for (const [price, size] of data.asks) {
      const p = parseFloat(price);
      const s = parseFloat(size);
      if (s > 0) {
        this.asks.set(p, s);
      }
    }
    
    this.lastSeqId = data.seqId;
    this.lastChecksum = data.checksum;
    
    console.log(`[OKX] Snapshot received: ${this.bids.size} bids, ${this.asks.size} asks`);
  }

  private processUpdate(data: any): void {
    // Apply bid updates
    for (const [price, size] of data.bids) {
      const p = parseFloat(price);
      const s = parseFloat(size);
      
      if (s === 0) {
        this.bids.delete(p);
      } else {
        this.bids.set(p, s);
      }
    }
    
    // Apply ask updates
    for (const [price, size] of data.asks) {
      const p = parseFloat(price);
      const s = parseFloat(size);
      
      if (s === 0) {
        this.asks.delete(p);
      } else {
        this.asks.set(p, s);
      }
    }
    
    this.lastSeqId = data.seqId;
    this.lastChecksum = data.checksum;
  }

  private processBufferedUpdates(): void {
    for (const update of this.updateBuffer) {
      if (update.data && update.data[0]) {
        // Check sequence continuity
        const data = update.data[0];
        if (data.prevSeqId && data.prevSeqId !== this.lastSeqId) {
          console.warn(`[OKX] Buffered update sequence mismatch`);
          continue;
        }
        this.processUpdate(data);
      }
    }
    this.updateBuffer = [];
  }

  private validateChecksum(expectedChecksum: number): boolean {
    // Get top 25 bids and asks for checksum
    const topBids = this.getBids(25);
    const topAsks = this.getAsks(25);
    
    // Build checksum string
    const parts: string[] = [];
    
    // Bids: price:size
    for (const { price, size } of topBids) {
      parts.push(`${this.formatPrice(price)}:${this.formatSize(size)}`);
    }
    
    // Asks: price:size
    for (const { price, size } of topAsks) {
      parts.push(`${this.formatPrice(price)}:${this.formatSize(size)}`);
    }
    
    const checksumString = parts.join(':');
    const calculated = crc32.str(checksumString) >>> 0;
    
    return calculated === expectedChecksum;
  }

  private formatPrice(price: number): string {
    // Remove trailing zeros
    const formatted = price.toFixed(8);
    return parseFloat(formatted).toString();
  }

  private formatSize(size: number): string {
    const formatted = size.toFixed(8);
    return parseFloat(formatted).toString();
  }

  private async resubscribe(): Promise<void> {
    console.log('[OKX] Resubscribing to orderbook...');
    this.isSnapshotReceived = false;
    this.updateBuffer = [];
    
    if (this.ws?.readyState === WebSocket.OPEN) {
      // Unsubscribe
      this.ws.send(JSON.stringify({
        op: 'unsubscribe',
        args: [{
          channel: this.channel,
          instId: this.symbol
        }]
      }));
      
      await new Promise(resolve => setTimeout(resolve, 100));
      
      // Resubscribe
      this.ws.send(JSON.stringify({
        op: 'subscribe',
        args: [{
          channel: this.channel,
          instId: this.symbol
        }]
      }));
    }
  }

  private async handleReconnect(): Promise<void> {
    console.log('[OKX] Reconnecting in 5 seconds...');
    await new Promise(resolve => setTimeout(resolve, 5000));
    this.isSnapshotReceived = false;
    this.updateBuffer = [];
    await this.connect();
  }

  onUpdate(callback: () => void): void {
    this.onUpdateCallback = callback;
  }

  getBids(limit?: number): OrderBookLevel[] {
    const sorted = Array.from(this.bids.entries())
      .map(([price, size]) => ({ price, size }))
      .sort((a, b) => b.price - a.price);
    
    return limit ? sorted.slice(0, limit) : sorted;
  }

  getAsks(limit?: number): OrderBookLevel[] {
    const sorted = Array.from(this.asks.entries())
      .map(([price, size]) => ({ price, size }))
      .sort((a, b) => a.price - b.price);
    
    return limit ? sorted.slice(0, limit) : sorted;
  }

  getBestBid(): OrderBookLevel | null {
    const bids = this.getBids(1);
    return bids.length > 0 ? bids[0] : null;
  }

  getBestAsk(): OrderBookLevel | null {
    const asks = this.getAsks(1);
    return asks.length > 0 ? asks[0] : null;
  }

  getSpread(): { absolute: number; percentage: number } | null {
    const bestBid = this.getBestBid();
    const bestAsk = this.getBestAsk();
    
    if (!bestBid || !bestAsk) return null;
    
    const absolute = bestAsk.price - bestBid.price;
    const percentage = (absolute / bestBid.price) * 100;
    
    return { absolute, percentage };
  }

  getMidPrice(): number | null {
    const bestBid = this.getBestBid();
    const bestAsk = this.getBestAsk();
    
    if (!bestBid || !bestAsk) return null;
    
    return (bestBid.price + bestAsk.price) / 2;
  }

  getImbalance(levels: number = 10): number {
    const bids = this.getBids(levels);
    const asks = this.getAsks(levels);
    
    const bidVolume = bids.reduce((sum, b) => sum + b.size, 0);
    const askVolume = asks.reduce((sum, a) => sum + a.size, 0);
    const total = bidVolume + askVolume;
    
    return total > 0 ? (bidVolume - askVolume) / total : 0;
  }

  getOrderBookStats(levels: number = 10): {
    bidVolume: number;
    askVolume: number;
    imbalance: number;
    spread: { absolute: number; percentage: number } | null;
    midPrice: number | null;
  } {
    const bids = this.getBids(levels);
    const asks = this.getAsks(levels);
    
    const bidVolume = bids.reduce((sum, b) => sum + b.size, 0);
    const askVolume = asks.reduce((sum, a) => sum + a.size, 0);
    const total = bidVolume + askVolume;
    
    return {
      bidVolume,
      askVolume,
      imbalance: total > 0 ? (bidVolume - askVolume) / total : 0,
      spread: this.getSpread(),
      midPrice: this.getMidPrice()
    };
  }

  disconnect(): void {
    this.stopPing();
    if (this.ws) {
      this.ws.close();
      this.ws = null;
    }
  }
}

// Usage Example
async function main() {
  const orderBook = new OkxLocalOrderBook('BTC-USDT-SWAP', 'books50-l2-tbt');
  
  orderBook.onUpdate(() => {
    const stats = orderBook.getOrderBookStats(10);
    console.log(`Mid: ${stats.midPrice?.toFixed(2)} | Spread: ${stats.spread?.percentage.toFixed(4)}% | Imbalance: ${stats.imbalance.toFixed(3)}`);
  });
  
  await orderBook.connect();
  
  // Keep running
  process.on('SIGINT', () => {
    orderBook.disconnect();
    process.exit(0);
  });
}

export { OkxLocalOrderBook, OrderBookLevel };
```

## Best Practices for Order Book Management

### 1. Channel Selection

| Use Case | Recommended Channel |
|----------|---------------------|
| Price display only | `books5` |
| Standard trading | `books50-l2-tbt` |
| Market making | `books-l2-tbt` |
| Historical analysis | `books` |

### 2. Sequence Validation

Always validate `prevSeqId` matches `lastSeqId` for update messages:

```typescript
if (data.prevSeqId !== this.lastSeqId) {
  // Gap detected - resubscribe
  this.resubscribe();
  return;
}
```

### 3. Checksum Validation

OKX provides CRC32 checksum for the top 25 price levels. Always validate:

```typescript
const calculated = crc32.str(checksumString) >>> 0;
if (calculated !== expectedChecksum) {
  // Order book corrupted - resubscribe
  this.resubscribe();
}
```

### 4. Buffer Updates Before Snapshot

Buffer all update messages until the first snapshot is received:

```typescript
if (!this.isSnapshotReceived) {
  this.updateBuffer.push(message);
  return;
}
```

### 5. Ping/Pong Management

OKX requires ping every 25-30 seconds. Track pong responses:

```typescript
setInterval(() => {
  if (Date.now() - lastPongTime > 30000) {
    // Connection stale
    reconnect();
  }
  ws.send('ping');
}, 25000);
```

### 6. Memory Management

Periodically clean up stale price levels:

```typescript
// Remove levels with zero size
for (const [price, size] of this.bids) {
  if (size === 0) this.bids.delete(price);
}
```

## Error Recovery Patterns

### Sequence Gap

```
Sequence gap detected -> Buffer updates -> Resubscribe -> Process buffered updates
```

### Checksum Mismatch

```
Checksum failed -> Log warning -> Resubscribe -> Rebuild order book
```

### Connection Loss

```
WebSocket close -> Wait 5s -> Reconnect -> Resubscribe -> Clear buffer
```

### Stale Connection

```
No pong for 30s -> Force close -> Reconnect -> Resubscribe
```

## Rate Limits

| Channel Type | Rate Limit |
|--------------|------------|
| Public WebSocket | 240 subscriptions per connection |
| Private WebSocket | 240 subscriptions per connection |
| Connections per IP | 3 connections |

## Related Documentation

- [OKX WebSocket API](https://www.okx.com/docs-v5/en/#order-book-trading-ws-books-channel)
- [OKX REST API](./en.md)
- [Best Practices](./trick.md)
