# 📚 Binance API Knowledge Base

Complete Binance API documentation with REST, WebSocket, and SDK references.

**Files:** 271

---

## 📁 Structure

```
binance/
├── spot/              # Spot Trading API
├── futures/           # Futures Trading API
├── options/           # Options Trading API
├── margin/            # Margin Trading API
├── wallet/            # Wallet Endpoints
├── sub-account/       # Sub-Account Management
├── mining/            # Mining Endpoints
├── stream/            # WebSocket Streams
├── fix/               # FIX Protocol
├── python/            # Python SDK
├── node/              # Node.js SDK
└── java/              # Java SDK
```

---

## 🔌 API Endpoints

### Spot API
```
REST:       https://api.binance.com
WebSocket:  wss://stream.binance.com:9443/ws
FIX:        fix-api.binance.com (port 9000)
```

### Futures API
```
USDT-M:     https://fapi.binance.com
Coin-M:     https://dapi.binance.com
WebSocket:  wss://fstream.binance.com/ws
```

### Options API
```
REST:       https://eapi.binance.com
WebSocket:  wss://voptions.binance.com/ws
```

---

## 📖 Key Topics

| Category | Description |
|----------|-------------|
| **Authentication** | HMAC, RSA, Ed25519 |
| **Orders** | Market, Limit, Stop, OCO |
| **Positions** | Open, Close, Modify |
| **Account** | Balance, Trade Fee, Status |
| **Market Data** | Ticker, Orderbook, Trades |
| **WebSocket** | Streams, Subscriptions |

---

## 🔗 Links

- [Official Docs](https://binance-docs.github.io/apidocs/)
- [API Status](https://www.binance.com/en/network-status)
- [Fees](https://www.binance.com/en/fee/schedule)

---

*Part of CITARION Knowledge Base*
