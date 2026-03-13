# 📚 Cornix API Knowledge Base

Cornix signal format and API integration documentation.

**Files:** 225

---

## 📁 Structure

```
cornix-api/
├── signal-format/          # Signal Parsing
├── api-integration/        # REST API
├── trading-functionalities/ # Feature API
├── channel-admins/         # Channel API
├── account-subscription/   # Account API
├── getting-started/        # API Setup
├── trading-bots/           # Bot API
├── trading-configurations/ # Config API
├── backtesting/            # Backtest API
├── marketplace/            # Marketplace API
├── demo-accounts/          # Demo API
├── errors-notifications/   # Error Codes
└── faqs-more/              # FAQ
```

---

## 📡 Signal Format

### Standard Signal
```
BTCUSDT
LONG
Entry: 67000-67200
TP1: 68000
TP2: 69000
SL: 66000
Leverage: 10x
```

### Multi-Entry Signal
```
BTCUSDT LONG

Entry 1: 67000 (25%)
Entry 2: 66500 (25%)
Entry 3: 66000 (50%)

TP1: 68000 (25%)
TP2: 69000 (25%)
TP3: 70000 (50%)

SL: 65000
```

---

## 🔌 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/v1/bots` | GET | List bots |
| `/api/v1/bots/:id` | GET | Bot details |
| `/api/v1/signals` | GET | Signal history |
| `/api/v1/positions` | GET | Open positions |
| `/api/v1/exchanges` | GET | Connected exchanges |

---

## ⚙️ Configuration

```json
{
  "botType": "DCA",
  "symbol": "BTCUSDT",
  "exchange": "binance",
  "leverage": 10,
  "maxPositions": 3,
  "takeProfit": 5,
  "stopLoss": 3,
  "trailingStop": {
    "enabled": true,
    "percent": 2
  }
}
```

---

## 🔗 Links

- [Cornix API](https://cornix.io/api)
- [Signal Providers](https://cornix.io/marketplace)

---

*Part of CITARION Knowledge Base*
