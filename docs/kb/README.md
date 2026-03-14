# 📚 Knowledge Base

External documentation from trading platforms, exchanges, and charting libraries.

**Total Files:** 3,659 markdown documents

---

## 📊 Statistics

### Exchange APIs

| Knowledge Base | Files | Source |
|----------------|-------|--------|
| **Binance API** | 276 | [binance-docs](https://binance-docs.github.io/apidocs/) |
| **OKX API** | 13 | [okx.com](https://www.okx.com/docs-v5/) |
| **Bybit API** | 1 | [bybit-exchange](https://bybit-exchange.github.io/docs/) |
| **Bitget API** | 1 | [bitget.com](https://www.bitget.com/api-doc/) |
| **BingX API** | 2 | [bingx-api](https://bingx-api.github.io/docs-v3/) |

### Trading Platforms

| Knowledge Base | Files | Source |
|----------------|-------|--------|
| **TradingView** | 2,980 | [tradingview.com](https://www.tradingview.com/) |
| **Pine Script** | 72 | [pine-script-docs](https://www.tradingview.com/pine-script-docs/) |
| **Lightweight Charts** | 76 | [lightweight-charts](https://tradingview.github.io/lightweight-charts/) |

### Trading Bots & Services

| Knowledge Base | Files | Source |
|----------------|-------|--------|
| **Cornix** | 237 | [cornix.io](https://cornix.io/) |

---

## 📁 Directory Structure

```
kb/
├── binance/              # Binance Exchange API (276 files)
│   ├── spot/            # Spot trading API
│   ├── futures/         # USDT-M & Coin-M futures
│   ├── options/         # European options
│   ├── margin/          # Margin trading
│   ├── python/          # Python SDK
│   ├── authentication.md    # Auth guide
│   ├── error-codes.md       # Error reference
│   ├── response-logging.md  # Logging guide
│   ├── trading.md           # Trading operations
│   └── websocket-streams.md # WebSocket docs
│
├── okx/                  # OKX Exchange API (13 files)
│   ├── README.md        # API Overview
│   ├── en.md            # Full API Documentation
│   ├── log.md           # API Change Log
│   ├── trick.md         # Best Practices & Tips
│   ├── broker.md        # Broker Program API
│   ├── agent.md         # Agent Program API
│   ├── repos/           # SDK repositories (Rust, TypeScript, Python)
│   │   ├── fairwic-okx-rs/    # Rust SDK
│   │   ├── rotyang-okx-rs/    # Rust SDK (alternative)
│   │   ├── npm-okx-api/       # TypeScript SDK
│   │   ├── pypi-okx-sdk/      # Python SDK
│   │   └── docs-rs-okx/       # Rust docs
│   └── media/           # Documentation images
│
├── bybit/                # Bybit Exchange API (1 file)
│   └── README.md        # Complete API Reference
│       # - Authentication (HMAC & RSA)
│       # - Market Data Endpoints
│       # - Trading Operations
│       # - WebSocket Streams
│       # - Position Management
│       # - Local Order Book Management
│       # - SDK References (Python, Node.js, Go, Java, .NET)
│
├── bitget/               # Bitget Exchange API (1 file)
│   └── README.md        # Complete API Reference
│       # - V2 API Overview
│       # - Spot & Futures Trading
│       # - WebSocket Streams
│       # - Position Management
│       # - Local Order Book Management
│       # - Rate Limit Best Practices
│       # - Error Recovery Patterns
│
├── bingx/                # BingX Exchange API (2 files)
│   ├── README.md        # Complete API Reference
│   │   # - Spot & Futures API
│   │   # - WebSocket Streams
│   │   # - Local Order Book Management
│   │   # - Rate Limit Best Practices
│   │   # - Error Recovery Patterns
│   └── SDK_WRAPPER.md   # TypeScript SDK Implementation
│       # - Full SDK wrapper for BingX API
│       # - Market data methods
│       # - Trading operations
│       # - Position management
│       # - WebSocket support
│       # - Error handling
│
├── tradingview/          # TradingView Platform (2,980 files)
│   ├── Widgets/         # All widgets
│   ├── chart/           # Chart features
│   ├── indicators/      # Built-in indicators
│   ├── trading/         # Trading features
│   ├── screener/        # Screener tools
│   ├── financials/      # Financial data
│   └── ...
│
├── pine-script/          # Pine Script Language (72 files)
│   ├── Language/        # Syntax & types
│   ├── Concepts/        # Core concepts
│   ├── Writing/         # Script guides
│   ├── Visuals/         # Visual elements
│   ├── Errors/          # Error reference
│   ├── Migration/       # Version migration guides
│   └── FAQ/             # Frequently asked questions
│
├── lightweight-charts/   # Lightweight Charts (76 files)
│   ├── docs/            # API docs
│   ├── tutorials/       # Tutorials
│   └── screenshots/     # Documentation images
│
└── cornix/               # Cornix Bot Platform (237 files)
    ├── getting-started/ # Account setup, API keys
    ├── trading-bots/    # Signals bot, Grid bot, DCA bot
    ├── trading-configurations/ # All trading settings
    ├── channel-admins/  # Channel management
    ├── errors-notifications/ # Error messages & notifications
    ├── account-subscription/ # Plans & billing
    ├── marketplace/     # Marketplace features
    ├── backtesting/     # Backtesting docs
    ├── demo-accounts/   # Demo trading
    ├── trading-functionalities/ # Manual trading features
    ├── faqs-more/       # FAQs and guides
    ├── affiliation-program/ # Affiliate program
    │
    └── Examples/        # Signal examples (8 folders)
        ├── Cornix_bot_control_telegram-example/
        ├── Cornix_notifications-example/
        └── Cornix_trading_channel-example1-6/
```

---

## 🔸 Exchange APIs

### Binance API

**Location:** [`binance/`](./binance/)

Complete Binance API documentation including Spot, Futures, Options, Margin, and SDKs.

**Key Endpoints:**
```
Spot:        https://api.binance.com
Futures USDT: https://fapi.binance.com
Futures Coin: https://dapi.binance.com
Options:     https://eapi.binance.com
WebSocket:   wss://stream.binance.com:9443/ws
```

**Key Files:**
- `authentication.md` - HMAC and RSA authentication
- `error-codes.md` - Error code reference
- `trading.md` - Trading operations guide
- `websocket-streams.md` - WebSocket documentation

### OKX API

**Location:** [`okx/`](./okx/)

Comprehensive OKX documentation with SDKs and implementation guides.

**Features:**
- Complete REST & WebSocket API documentation
- Multiple SDK repositories:
  - `fairwic-okx-rs` - Rust SDK with full API support
  - `rotyang-okx-rs` - Rust SDK with order book management
  - `npm-okx-api` - TypeScript SDK
  - `pypi-okx-sdk` - Python SDK
- Local Order Book Management implementation
- Broker & Agent program APIs

**Key Endpoints:**
```
REST:        https://www.okx.com
WebSocket:   wss://ws.okx.com:8443/ws/v5/public
```

### Bybit API

**Location:** [`bybit/`](./bybit/)

Complete V5 API reference with all product lines unified.

**Features:**
- Unified V5 API for all products (Spot, Linear, Inverse, Option)
- HMAC and RSA authentication
- Local Order Book Management
- Official SDKs: Python, Node.js, Go, Java, .NET

**Key Endpoints:**
```
Mainnet:     https://api.bybit.com
Testnet:     https://api-testnet.bybit.com
WebSocket:   wss://stream.bybit.com/v5/public/linear
```

### Bitget API

**Location:** [`bitget/`](./bitget/)

V2 API documentation for Spot and Futures trading.

**Features:**
- Unified V2 API
- Spot, Margin, Futures support
- Copy Trading endpoints
- Local Order Book Management

**Key Endpoints:**
```
REST:        https://api.bitget.com
WebSocket:   wss://ws.bitget.com/v2/ws/public
```

### BingX API

**Location:** [`bingx/`](./bingx/)

API documentation with TypeScript SDK wrapper implementation.

**Features:**
- Spot & Standard Contract (Futures) API
- Complete TypeScript SDK implementation
- WebSocket market data streams
- Local Order Book Management

**Key Endpoints:**
```
REST:        https://open-api.bingx.com
WebSocket:   wss://open-api-swap.bingx.com/openapi/swap/v2/ws
```

---

## 🔸 Trading Platforms

### TradingView

**Location:** [`tradingview/`](./tradingview/)

Complete TradingView platform documentation including widgets, features, and chart types.

### Pine Script

**Location:** [`pine-script/`](./pine-script/)

Pine Script v5/v6 programming language reference for custom indicators and strategies.

**Sections:**
- `Language/` - Syntax, types, operators
- `Concepts/` - Strategies, alerts, timeframes
- `Writing/` - Script development guides
- `Visuals/` - Plots, colors, tables
- `Errors/` - Error code reference
- `Migration/` - Version migration guides

### Lightweight Charts

**Location:** [`lightweight-charts/`](./lightweight-charts/)

TradingView's open-source charting library with API documentation and examples.

**GitHub:** https://github.com/tradingview/lightweight-charts

---

## 🔸 Trading Bots & Services

### Cornix

**Location:** [`cornix/`](./cornix/)

Cornix trading bot platform documentation - complete Help Center Knowledge Base.

**Sections:**
- `getting-started/` - Account creation, API keys for all exchanges
- `trading-bots/` - Signals Bot, Grid Bot, DCA Bot, TradingView Bot
- `trading-configurations/` - All trading settings (leverage, stop-loss, take-profit, etc.)
- `channel-admins/` - Signal channel management
- `errors-notifications/` - Error codes and notification messages
- `account-subscription/` - Subscription plans and billing
- `marketplace/` - Marketplace features and statistics
- `demo-accounts/` - Risk-free demo trading
- `trading-functionalities/` - Manual trading features
- `faqs-more/` - FAQs and trading guides
- `affiliation-program/` - Affiliate program

**Example Folders (8 examples):**
- `Cornix_bot_control_telegram-example/` - Bot control via Telegram
- `Cornix_notifications-example/` - Notification formats
- `Cornix_trading_channel-example1-6/` - Trading channel signal formats

---

## 📖 Usage

This Knowledge Base is used for:

1. **AI-Assisted Development** - Reference for building trading features
2. **API Integration** - Exchange and platform integration
3. **Indicator Development** - Technical indicator implementations
4. **Signal Processing** - Signal format parsing and validation
5. **SDK Development** - Building wrappers for exchange APIs

---

## 🔗 External Links

### Exchanges
- [Binance API Docs](https://binance-docs.github.io/apidocs/)
- [OKX API Docs](https://www.okx.com/docs-v5/)
- [Bybit API Docs](https://bybit-exchange.github.io/docs/)
- [Bitget API Docs](https://www.bitget.com/api-doc/)
- [BingX API Docs](https://bingx-api.github.io/docs-v3/)

### Trading Platforms
- [TradingView](https://www.tradingview.com/)
- [Pine Script Reference](https://www.tradingview.com/pine-script-docs/)
- [Lightweight Charts](https://tradingview.github.io/lightweight-charts/)

### Trading Bots
- [Cornix](https://cornix.io/)

---

*Knowledge Base for CITARION Algorithmic Trading Platform*
*Last Updated: March 2026*
