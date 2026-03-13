# 📚 Knowledge Base

External documentation from trading platforms, exchanges, and charting libraries.

**Total Files:** 3,933 markdown documents

---

## 📊 Statistics

| Knowledge Base | Files | Source |
|----------------|-------|--------|
| **Binance API** | 271 | [binance-docs](https://binance-docs.github.io/apidocs/) |
| **TradingView** | 2,980 | [tradingview.com](https://www.tradingview.com/) |
| **Pine Script** | 72 | [pine-script-docs](https://www.tradingview.com/pine-script-docs/) |
| **Lightweight Charts** | 76 | [lightweight-charts](https://tradingview.github.io/lightweight-charts/) |
| **Cornix** | 237 | [cornix.io](https://cornix.io/) |
| **Cornix API** | 225 | Cornix API documentation |

---

## 📁 Directory Structure

```
kb/
├── binance/              # Binance Exchange API (271 files)
│   ├── spot/            # Spot trading API
│   ├── futures/         # USDT-M & Coin-M futures
│   ├── options/         # European options
│   ├── margin/          # Margin trading
│   ├── python/          # Python SDK
│   └── ...
│
├── tradingview/          # TradingView Platform (2,980 files)
│   ├── Widgets/         # All widgets
│   ├── chart/           # Chart features
│   ├── indicators/      # Built-in indicators
│   ├── trading/         # Trading features
│   ├── screener/        # Screener tools
│   └── ...
│
├── pine-script/          # Pine Script Language (72 files)
│   ├── Language/        # Syntax & types
│   ├── Concepts/        # Core concepts
│   ├── Writing/         # Script guides
│   ├── Visuals/         # Visual elements
│   └── Errors/          # Error reference
│
├── lightweight-charts/   # Lightweight Charts (76 files)
│   ├── docs/            # API docs
│   ├── tutorials/       # Tutorials
│   └── plugins/         # Plugin docs
│
├── cornix/               # Cornix Bot Platform (237 files)
│   ├── getting-started/ # Quick start
│   ├── trading-bots/    # Bot types
│   ├── backtesting/     # Backtesting
│   └── ...
│
└── cornix-api/           # Cornix API (225 files)
    ├── signal-format/   # Signal parsing
    └── api/             # API integration
```

---

## 🔸 Binance API

**Location:** [`binance/`](./binance/)

Complete Binance API documentation including:

### Spot API
- REST API endpoints
- WebSocket streams
- FIX protocol
- Order management
- Account endpoints

### Futures API
- USDT-M Futures
- Coin-M Futures
- Leverage trading
- Position management

### Other
- Options API
- Margin Trading
- OAuth Login
- Python SDK

**Key Endpoints:**
```
Spot:        https://api.binance.com
Futures USDT: https://fapi.binance.com
Futures Coin: https://dapi.binance.com
Options:     https://eapi.binance.com
WebSocket:   wss://stream.binance.com:9443/ws
```

---

## 🔸 TradingView

**Location:** [`tradingview/`](./tradingview/)

Complete TradingView platform documentation:

### Widgets
- Advanced Chart Widget
- Mini Chart Widget
- Heatmaps
- Screeners
- Tickers

### Features
- Chart types and indicators
- Drawing tools
- Alerts
- Trading panel
- Social features

---

## 🔸 Pine Script

**Location:** [`pine-script/`](./pine-script/)

Pine Script v5/v6 programming language reference:

### Language
- Syntax and semantics
- Data types
- Operators
- Built-in functions

### Concepts
- Series and variables
- Arrays and matrices
- Drawing and visual elements
- Strategies and indicators

---

## 🔸 Lightweight Charts

**Location:** [`lightweight-charts/`](./lightweight-charts/)

TradingView's open-source charting library:

### Features
- Multiple chart types
- Custom indicators
- Price scales
- Time scales
- Plugins support

**GitHub:** https://github.com/tradingview/lightweight-charts

---

## 🔸 Cornix

**Location:** [`cornix/`](./cornix/) | [`cornix-api/`](./cornix-api/)

Cornix trading bot platform documentation:

### Platform
- Bot configuration
- Signal providers
- Backtesting
- Risk management

### API
- Signal format specification
- Channel admin API
- Trading functionalities

---

## 📖 Usage

This Knowledge Base is used for:

1. **AI-Assisted Development** - Reference for building trading features
2. **API Integration** - Exchange and platform integration
3. **Indicator Development** - Technical indicator implementations
4. **Signal Processing** - Signal format parsing and validation

---

## 🔗 External Links

- [Binance API Docs](https://binance-docs.github.io/apidocs/)
- [TradingView](https://www.tradingview.com/)
- [Pine Script Reference](https://www.tradingview.com/pine-script-docs/)
- [Lightweight Charts](https://tradingview.github.io/lightweight-charts/)
- [Cornix](https://cornix.io/)

---

*Knowledge Base for CITARION Algorithmic Trading Platform*
