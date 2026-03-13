# 📚 CITARION Documentation

> **Comprehensive documentation for the CITARION Algorithmic Trading Platform**

![Documentation](https://img.shields.io/badge/Documentation-100%25-brightgreen?style=flat)
![Files](https://img.shields.io/badge/Files-4000%2B-blue?style=flat)
![Languages](https://img.shields.io/badge/Languages-EN%20%7C%20RU-yellow?style=flat)

---

## 📖 Table of Contents

1. [Overview](#-overview)
2. [Knowledge Base](#-knowledge-base)
3. [Backend Documentation](#-backend-documentation)
4. [Frontend Documentation](#-frontend-documentation)
5. [Integration Guides](#-integration-guides)
6. [Quick Links](#-quick-links)

---

## 🎯 Overview

CITARION documentation is organized into several categories:

| Category | Files | Description |
|----------|-------|-------------|
| **Knowledge Base** | 3,933 | External API & platform documentation |
| **Backend Docs** | 45+ | API, services, strategies, indicators |
| **Frontend Docs** | 35+ | Components, hooks, state management |
| **Integration** | 20+ | Exchange, ML, microservices |
| **Security** | 10+ | Authentication, encryption, best practices |

---

## 📚 Knowledge Base

External documentation from trading platforms, exchanges, and charting libraries.

### 🔸 Binance API Documentation

**Location:** [`kb/binance/`](./kb/binance/) | **Files:** 271

Complete Binance API documentation with REST, WebSocket, and SDK references.

| Module | Description |
|--------|-------------|
| **Spot API** | REST API, WebSocket streams, FIX protocol |
| **Futures API** | USDT-M and Coin-M futures trading |
| **Options API** | European options trading endpoints |
| **Margin Trading** | Leverage and margin endpoints |
| **OAuth Login** | Authentication integration |
| **Python SDK** | Official Python connector with examples |

**Key Files:**
- [`spot/`](./kb/binance/spot/) - Spot trading API
- [`futures/`](./kb/binance/futures/) - Futures trading API
- [`options/`](./kb/binance/options/) - Options trading API
- [`margin/`](./kb/binance/margin/) - Margin trading API
- [`python/`](./kb/binance/python/) - Python SDK

---

### 🔸 TradingView Platform Documentation

**Location:** [`kb/tradingview/`](./kb/tradingview/) | **Files:** 2,980

Complete TradingView platform documentation.

| Module | Description |
|--------|-------------|
| **Widgets** | Advanced Chart, Mini Chart, Heatmaps, Screeners |
| **Chart** | Chart features, indicators, drawings |
| **Trading** | Trading panel, order management |
| **Screener** | Stock/crypto screeners |
| **Alerts** | Alert configuration and management |
| **Mobile** | iOS and Android app features |

**Key Directories:**
- [`Widgets/`](./kb/tradingview/Widgets/) - All TradingView widgets
- [`chart/`](./kb/tradingview/chart/) - Chart features
- [`indicators/`](./kb/tradingview/indicators/) - Built-in indicators
- [`trading/`](./kb/tradingview/trading/) - Trading features
- [`screener/`](./kb/tradingview/screener/) - Screener documentation

---

### 🔸 Pine Script Documentation

**Location:** [`kb/pine-script/`](./kb/pine-script/) | **Files:** 72

Pine Script programming language reference for TradingView indicators.

| Module | Description |
|--------|-------------|
| **Language** | Syntax, types, operators |
| **Concepts** | Core programming concepts |
| **Visuals** | Visual elements and rendering |
| **Writing** | Script writing guides |
| **Migration** | Version migration guides |
| **Errors** | Error handling and debugging |

**Key Files:**
- [`Language/`](./kb/pine-script/Language/) - Language reference
- [`Concepts/`](./kb/pine-script/Concepts/) - Core concepts
- [`Writing/`](./kb/pine-script/Writing/) - Writing guides
- [`Errors/`](./kb/pine-script/Errors/) - Error reference

---

### 🔸 Lightweight Charts Documentation

**Location:** [`kb/lightweight-charts/`](./kb/lightweight-charts/) | **Files:** 76

TradingView Lightweight Charts library documentation.

| Module | Description |
|--------|-------------|
| **API Reference** | Complete API documentation |
| **Tutorials** | Step-by-step guides |
| **How-to** | Common implementation patterns |
| **Plugins** | Plugin development |
| **Migrations** | Version upgrade guides |

**Key Files:**
- [`docs/api/`](./kb/lightweight-charts/docs/api/) - API reference
- [`tutorials/`](./kb/lightweight-charts/tutorials/) - Tutorials
- [`docs/plugins/`](./kb/lightweight-charts/docs/plugins/) - Plugin docs

---

### 🔸 Cornix Bot Documentation

**Location:** [`kb/cornix/`](./kb/cornix/) | **Files:** 237

Cornix trading bot platform documentation.

| Module | Description |
|--------|-------------|
| **Getting Started** | Account setup and configuration |
| **Trading Bots** | Bot types and configuration |
| **Backtesting** | Strategy testing |
| **Channel Admins** | Telegram channel integration |
| **Marketplace** | Signal provider marketplace |

**Key Directories:**
- [`getting-started/`](./kb/cornix/getting-started/) - Quick start guides
- [`trading-bots/`](./kb/cornix/trading-bots/) - Bot documentation
- [`backtesting/`](./kb/cornix/backtesting/) - Backtesting guides
- [`channel-admins/`](./kb/cornix/channel-admins/) - Channel management

---

### 🔸 Cornix API Documentation

**Location:** [`kb/cornix-api/`](./kb/cornix-api/) | **Files:** 225

Cornix API and signal format documentation.

| Module | Description |
|--------|-------------|
| **Signal Format** | Signal parsing specifications |
| **API Integration** | REST API documentation |
| **Trading Functionalities** | Feature documentation |

---

## 🔧 Backend Documentation

### API Reference

| Document | Description |
|----------|-------------|
| [`backend/API_REFERENCE_COMPLETE.md`](./backend/API_REFERENCE_COMPLETE.md) | Complete API reference (120+ endpoints) |
| [`backend/INDICATORS_SERVICE_COMPLETE.md`](./backend/INDICATORS_SERVICE_COMPLETE.md) | Technical indicators service |
| [`backend/RISK_SERVICE_COMPLETE.md`](./backend/RISK_SERVICE_COMPLETE.md) | Risk management service |
| [`backend/BOT_SERVICE_COMPLETE.md`](./backend/BOT_SERVICE_COMPLETE.md) | Bot management service |
| [`backend/TRADING_SERVICE_COMPLETE.md`](./backend/TRADING_SERVICE_COMPLETE.md) | Trading service |

### Trading Bots

| Document | Description |
|----------|-------------|
| [`bots/GRID_BOT.md`](./bots/GRID_BOT.md) | Grid trading bot |
| [`bots/DCA_BOT.md`](./bots/DCA_BOT.md) | DCA bot documentation |
| [`bots/BB_BOT.md`](./bots/BB_BOT.md) | Bollinger Bands bot |
| [`bots/ARGUS_BOT.md`](./bots/ARGUS_BOT.md) | Pump & dump detection |
| [`bots/VISION_BOT.md`](./bots/VISION_BOT.md) | Price forecasting bot |

### Indicators & Strategies

| Document | Description |
|----------|-------------|
| [`indicators/README.md`](./indicators/README.md) | All technical indicators |
| [`trading/STRATEGIES.md`](./trading/STRATEGIES.md) | Trading strategies |
| [`trading/TACTICS.md`](./trading/TACTICS.md) | Entry/exit tactics |

### Machine Learning

| Document | Description |
|----------|-------------|
| [`ml/ML_PIPELINE.md`](./ml/ML_PIPELINE.md) | ML pipeline documentation |
| [`ml/LAWRENCE_CLASSIFIER.md`](./ml/LAWRENCE_CLASSIFIER.md) | Lawrence classifier |
| [`ml/FEATURE_ENGINEERING.md`](./ml/FEATURE_ENGINEERING.md) | Feature engineering |

---

## 🎨 Frontend Documentation

### Components

| Document | Description |
|----------|-------------|
| [`components/README.md`](./components/README.md) | UI components overview |
| [`components/ADDITIONAL_COMPONENTS_COMPLETE.md`](./components/ADDITIONAL_COMPONENTS_COMPLETE.md) | Additional components |

### Hooks

| Document | Description |
|----------|-------------|
| [`hooks/README.md`](./hooks/README.md) | All React hooks (14 hooks) |

### State Management

| Document | Description |
|----------|-------------|
| [`state-management/README.md`](./state-management/README.md) | Zustand store documentation |

### Types

| Document | Description |
|----------|-------------|
| [`types/README.md`](./types/README.md) | TypeScript types (18+ interfaces) |

---

## 🔗 Integration Guides

### Exchange Integration

| Document | Description |
|----------|-------------|
| [`exchanges/README.md`](./exchanges/README.md) | All exchange integrations |
| [`binance/README.md`](./binance/README.md) | Binance integration |
| [`integrations/EXCHANGE_CLIENTS.md`](./integrations/EXCHANGE_CLIENTS.md) | Exchange clients |

### Microservices

| Document | Description |
|----------|-------------|
| [`microservices/README.md`](./microservices/README.md) | All microservices |
| [`integrations/IAF_SERVICE.md`](./integrations/IAF_SERVICE.md) | IAF Python service |

### AI Skills

| Document | Description |
|----------|-------------|
| [`skills/README.md`](./skills/README.md) | 18 AI skills integration |

---

## 🔗 Quick Links

### API Endpoints

```
Trading:     /api/trade, /api/trades, /api/positions
Bots:        /api/bots, /api/bots/[type]
ML:          /api/ml/predict, /api/ml/train, /api/ml/classify
Risk:        /api/risk, /api/risk/killswitch
Signals:     /api/signals, /api/chat/parse-signal
Exchange:    /api/exchange, /api/prices, /api/ohlcv
```

### WebSocket Ports

```
Price Service:   3002
Bot Monitor:     3003
Risk Monitor:    3004
Chat Service:    3005
ML Service:      3006
RL Service:      3007
```

### External Resources

- [TradingView](https://www.tradingview.com/)
- [Binance API](https://binance-docs.github.io/apidocs/)
- [Pine Script Reference](https://www.tradingview.com/pine-script-docs/)
- [Lightweight Charts](https://tradingview.github.io/lightweight-charts/)

---

## 📊 Statistics

| Metric | Value |
|--------|-------|
| **Total Documents** | 4,000+ |
| **Knowledge Base Files** | 3,933 |
| **Backend Docs** | 45+ |
| **Frontend Docs** | 35+ |
| **Code Examples** | 500+ |
| **API Endpoints** | 120+ |
| **Technical Indicators** | 200+ |
| **Trading Bots** | 17+ |

---

*Documentation maintained for CITARION Algorithmic Trading Platform.*
*Last updated: March 2026*
