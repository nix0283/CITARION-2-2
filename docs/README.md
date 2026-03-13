# CITARION Documentation

**Version:** 2.0 | **Last Updated:** March 2026 | **Total Documents:** 180+ | **Coverage:** 100% ✅

---

## 📚 Documentation Structure

### 🏗️ Architecture (`architecture/`)
Core system architecture documentation.

| Document | Description |
|----------|-------------|
| [API_SPECIFICATION.md](architecture/API_SPECIFICATION.md) | REST API endpoints, WebSocket protocols |
| [DATABASE_SCHEMA.md](architecture/DATABASE_SCHEMA.md) | Prisma models, ER diagrams, indexes |
| [FRONTEND_ARCHITECTURE.md](architecture/FRONTEND_ARCHITECTURE.md) | Component structure, state management |
| [WEBSOCKET_PROTOCOL.md](architecture/WEBSOCKET_PROTOCOL.md) | Real-time communication specs |
| [API_VERSIONING_STRATEGY.md](architecture/API_VERSIONING_STRATEGY.md) | API versioning and deprecation |
| [ARCHITECTURE_DECISION_RECORDS.md](architecture/ARCHITECTURE_DECISION_RECORDS.md) | ADRs for major decisions |
| [ORCHESTRATION_ARCHITECTURE.md](architecture/ORCHESTRATION_ARCHITECTURE.md) | Service orchestration |
| [ORCHESTRATION_LAYER.md](architecture/ORCHESTRATION_LAYER.md) | Orchestration layer details |

### 💼 Business Logic (`business-logic/`)
Trading logic, risk models, and compliance.

| Document | Description |
|----------|-------------|
| [BOT_ALGORITHMS.md](business-logic/BOT_ALGORITHMS.md) | Grid, DCA, BB algorithm details |
| [EXCHANGE_INTEGRATION_GUIDE.md](business-logic/EXCHANGE_INTEGRATION_GUIDE.md) | Exchange adapter implementation |
| [ML_MODELS_DOCUMENTATION.md](business-logic/ML_MODELS_DOCUMENTATION.md) | ML model specifications |
| [USER_MANUAL.md](business-logic/USER_MANUAL.md) | End-user documentation |
| [ADMIN_GUIDE.md](business-logic/ADMIN_GUIDE.md) | Administrator documentation |
| [RISK_MODELS_DOCUMENTATION.md](business-logic/RISK_MODELS_DOCUMENTATION.md) | VaR, CVaR, position sizing |
| [MARKET_DATA_SPECIFICATION.md](business-logic/MARKET_DATA_SPECIFICATION.md) | OHLCV, tickers, order books |
| [ORDER_EXECUTION_LOGIC.md](business-logic/ORDER_EXECUTION_LOGIC.md) | Order lifecycle, execution |
| [AUDIT_TRAIL_SPECIFICATION.md](business-logic/AUDIT_TRAIL_SPECIFICATION.md) | Audit logging specs |
| [COMPLIANCE_GUIDE.md](business-logic/COMPLIANCE_GUIDE.md) | Regulatory compliance |
| [BUSINESS_REQUIREMENTS.md](business-logic/BUSINESS_REQUIREMENTS.md) | Product requirements |

### 🚀 Deployment (`deployment/`)
Infrastructure and deployment guides.

| Document | Description |
|----------|-------------|
| [DEPLOYMENT_GUIDE.md](deployment/DEPLOYMENT_GUIDE.md) | Production deployment steps |
| [ENVIRONMENT_VARIABLES.md](deployment/ENVIRONMENT_VARIABLES.md) | All environment variables |
| [DISASTER_RECOVERY_PLAN.md](deployment/DISASTER_RECOVERY_PLAN.md) | DR procedures |
| [INCIDENT_RESPONSE_PLAYBOOK.md](deployment/INCIDENT_RESPONSE_PLAYBOOK.md) | Incident handling |
| [MONITORING_AND_ALERTING.md](deployment/MONITORING_AND_ALERTING.md) | Prometheus, Grafana setup |
| [PERFORMANCE_TUNING.md](deployment/PERFORMANCE_TUNING.md) | Optimization guide |
| [CAPACITY_PLANNING.md](deployment/CAPACITY_PLANNING.md) | Resource sizing |

### 💻 Development (`development/`)
Developer guides and standards.

| Document | Description |
|----------|-------------|
| [CONTRIBUTING.md](development/CONTRIBUTING.md) | Contribution guidelines |
| [TESTING_STRATEGY.md](development/TESTING_STRATEGY.md) | Test coverage requirements |
| [ERROR_HANDLING.md](development/ERROR_HANDLING.md) | Error codes, handling patterns |
| [TROUBLESHOOTING.md](development/TROUBLESHOOTING.md) | Common issues and solutions |

### 🤖 Bots (`bots/`)
Trading bot documentation.

| Document | Description |
|----------|-------------|
| [BOT_CODES_STANDARD.md](bots/BOT_CODES_STANDARD.md) | Bot development standards |
| [BOT_MANAGER_API.md](bots/BOT_MANAGER_API.md) | Bot management API |
| [GRID_BOT_IMPLEMENTATION.md](bots/GRID_BOT_IMPLEMENTATION.md) | Grid bot details |
| [INSTITUTIONAL_BOTS.md](bots/INSTITUTIONAL_BOTS.md) | Institutional bot types |
| [LOGOS_BOT.md](bots/LOGOS_BOT.md) | Self-learning bot |
| [LOGOS_SELF_LEARNING.md](bots/LOGOS_SELF_LEARNING.md) | Self-learning architecture |
| [RANGE_BOT.md](bots/RANGE_BOT.md) | Range trading bot |
| [ORION_BOT.md](bots/ORION_BOT.md) | Trend detection bot |
| [FREQUENCY_BOTS.md](bots/FREQUENCY_BOTS.md) | HFT, MFT, LFT bots |
| [BOT_ACTIVATION.md](bots/BOT_ACTIVATION.md) | Bot activation guide |
| [VISION_V2.md](bots/VISION_V2.md) | **Vision V2 with online learning** |

### 🔧 Microservices (`microservices/`)
Microservice architecture and APIs.

| Service | Port | Document | Description |
|---------|------|----------|-------------|
| Price Service | 3002 | [price-service.md](microservices/price-service.md) | Multi-exchange price aggregation |
| Bot Monitor | 3003 | [bot-monitor-service.md](microservices/bot-monitor-service.md) | Real-time bot monitoring |
| Trade Events | 3003 | [trade-events-service.md](microservices/trade-events-service.md) | Trade confirmations |
| Risk Monitor | 3004 | [risk-monitor-service.md](microservices/risk-monitor-service.md) | Risk metrics WebSocket |
| Chat Service | 3005 | [chat-service.md](microservices/chat-service.md) | Oracle AI assistant |
| HFT Service | 3005 | [hft-service.md](microservices/hft-service.md) | High-frequency trading (Go) |
| Telegram Service | 3006 | [telegram-service.md](microservices/telegram-service.md) | Telegram Bot |
| ML Service | 3006 | [ml-service.md](microservices/ml-service.md) | ML predictions (Python) |
| RL Service | 3007 | [rl-service.md](microservices/rl-service.md) | Reinforcement learning |

**Microservice Documentation:**
| Document | Description |
|----------|-------------|
| [README.md](microservices/README.md) | Microservices overview |
| [MICROSERVICES_API.md](microservices/MICROSERVICES_API.md) | All service APIs |
| [MICROSERVICES_DEPLOYMENT.md](microservices/MICROSERVICES_DEPLOYMENT.md) | Service deployment |
| [MICROSERVICES_MONITORING.md](microservices/MICROSERVICES_MONITORING.md) | Service monitoring |
| [MICROSERVICES_COMMUNICATION.md](microservices/MICROSERVICES_COMMUNICATION.md) | Inter-service communication |
| [MICROSERVICES_LOGGING.md](microservices/MICROSERVICES_LOGGING.md) | Logging standards |
| [MICROSERVICES_TRACING.md](microservices/MICROSERVICES_TRACING.md) | Distributed tracing |
| [MICROSERVICES_TESTING.md](microservices/MICROSERVICES_TESTING.md) | Service testing |

### 🧠 ML (`ml/`)
Machine learning documentation.

| Document | Description |
|----------|-------------|
| [ML_INTEGRATION.md](ml/ML_INTEGRATION.md) | ML integration overview |
| [ML_SIGNAL_PIPELINE.md](ml/ML_SIGNAL_PIPELINE.md) | Signal processing pipeline |
| [ML_BOT_INTEGRATION.md](ml/ML_BOT_INTEGRATION.md) | Bot-ML integration |
| [ML_LORENTZIAN_CLASSIFICATION.md](ml/ML_LORENTZIAN_CLASSIFICATION.md) | Lorentzian classifier |
| [ML_LORENTZIAN_EXTENSIONS.md](ml/ML_LORENTZIAN_EXTENSIONS.md) | Extensions |
| [ML_INDICATORS_AND_FILTERS.md](ml/ML_INDICATORS_AND_FILTERS.md) | ML indicators |
| [ML_RL_SERVICES.md](ml/ML_RL_SERVICES.md) | Reinforcement learning |
| [GENETIC_ALGORITHM.md](ml/GENETIC_ALGORITHM.md) | GA optimization |
| [GENETIC_ALGORITHM_OPTIMIZER.md](ml/GENETIC_ALGORITHM_OPTIMIZER.md) | GA optimizer |
| [GARCH_VOLATILITY_ANALYSIS.md](ml/GARCH_VOLATILITY_ANALYSIS.md) | Volatility modeling |
| [ML_PIPELINE_IMMEDIATE.md](ml/ML_PIPELINE_IMMEDIATE.md) | Pipeline guide |
| [MODEL_VERSIONING.md](ml/MODEL_VERSIONING.md) | Model versioning |
| [MODEL_MONITORING.md](ml/MODEL_MONITORING.md) | Model monitoring |
| [ML_PIPELINE_CI_CD.md](ml/ML_PIPELINE_CI_CD.md) | ML CI/CD pipeline |

### 📈 Trading (`trading/`)
Trading-specific documentation.

| Document | Description |
|----------|-------------|
| [TRADING_SYSTEM_ARCHITECTURE.md](trading/TRADING_SYSTEM_ARCHITECTURE.md) | System architecture |
| [CORNIX_SIGNAL_FORMAT.md](trading/CORNIX_SIGNAL_FORMAT.md) | Cornix signal parsing |
| [OHLCV-SYSTEM.md](trading/OHLCV-SYSTEM.md) | OHLCV data management |
| [indicators.md](trading/indicators.md) | Technical indicators |
| [tradingview-templates.md](trading/tradingview-templates.md) | TradingView integration |
| [copy-trading.md](trading/copy-trading.md) | Copy trading guide |
| [parameters-mapping.md](trading/parameters-mapping.md) | Parameter mapping |

### 🔗 Integrations (`integrations/`, `integration/`)
Third-party integrations.

| Document | Description |
|----------|-------------|
| [WEBHOOK_INTEGRATION.md](integration/WEBHOOK_INTEGRATION.md) | Webhook setup |
| [THIRD_PARTY_INTEGRATIONS.md](integration/THIRD_PARTY_INTEGRATIONS.md) | All third-party services |
| [ORACLE_INTEGRATION.md](integrations/ORACLE_INTEGRATION.md) | Oracle AI integration |
| [GB_INTEGRATION.md](integrations/GB_INTEGRATION.md) | Gradient Boosting |
| [wolfbot.md](integrations/wolfbot.md) | WolfBot integration |
| [profitmaker.md](integrations/profitmaker.md) | ProfitMaker integration |
| [iaf.md](integrations/iaf.md) | IAF integration |
| [integration-zenbot-abu.md](integrations/integration-zenbot-abu.md) | Zenbot/Abu integration |
| [IAF_SERVICE.md](integrations/IAF_SERVICE.md) | **IAF Service Complete (6 strategies, 18+ indicators)** |

### 🗃️ State Management (`state-management/`)
Zustand store documentation.

| Document | Description |
|----------|-------------|
| [README.md](state-management/README.md) | **Complete store documentation (7 slices, 20+ actions)** |

### 📝 TypeScript Types (`types/`)
TypeScript type definitions.

| Document | Description |
|----------|-------------|
| [README.md](types/README.md) | **Complete types documentation (18+ interfaces, type guards)** |

### 🪝 React Hooks (`hooks/`)
React hooks documentation.

| Document | Description |
|----------|-------------|
| [README.md](hooks/README.md) | **All 14 hooks documented with examples** |

### 🤖 AI Skills (`skills/`)
AI capabilities and skills integration.

| Document | Description |
|----------|-------------|
| [README.md](skills/README.md) | **Skills integration guide (18 skills, SDK usage)** |

### 📁 Examples (`examples/`)
Code examples and templates.

| Document | Description |
|----------|-------------|
| [README.md](examples/README.md) | **WebSocket examples with documentation** |

### 📦 Exchanges (`exchanges/`, `binance/`)
Exchange-specific documentation.

| Directory | Description |
|-----------|-------------|
| [exchanges/README.md](exchanges/README.md) | Exchange overview |
| [exchanges/binance/](exchanges/binance/) | Binance API docs |
| [exchanges/bybit/](exchanges/bybit/) | Bybit API docs |
| [exchanges/okx/](exchanges/okx/) | OKX API docs |
| [exchanges/bitget/](exchanges/bitget/) | Bitget API docs |
| [exchanges/bingx/](exchanges/bingx/) | BingX API docs |
| [exchanges/kucoin/](exchanges/kucoin/) | KuCoin API docs |
| [exchanges/htx/](exchanges/htx/) | HTX/Huobi API docs |
| [exchanges/hyperliquid/](exchanges/hyperliquid/) | HyperLiquid API docs |
| [exchanges/bitmex/](exchanges/bitmex/) | BitMEX API docs |
| [exchanges/blofin/](exchanges/blofin/) | BloFin API docs |
| [exchanges/coinbase/](exchanges/coinbase/) | Coinbase API docs |
| [exchanges/aster/](exchanges/aster/) | Aster DEX API docs |

**Exchange Guides:**
| Document | Description |
|----------|-------------|
| [TRADING_FEES.md](exchanges/TRADING_FEES.md) | Fee comparison |
| [error-codes.md](exchanges/error-codes.md) | Error codes |
| [COMPLIANCE_REPORT.md](exchanges/COMPLIANCE_REPORT.md) | Compliance |
| [EXCHANGE_FAILOVER.md](exchanges/EXCHANGE_FAILOVER.md) | Failover strategy |
| [EXCHANGE_HEALTH_CHECK.md](exchanges/EXCHANGE_HEALTH_CHECK.md) | Health checks |

### 🔧 Frameworks (`frameworks/`)
Framework documentation.

| Document | Description |
|----------|-------------|
| [shadcn-ui.md](frameworks/shadcn-ui.md) | UI components |
| [prisma.md](frameworks/prisma.md) | Database ORM |
| [next-auth.md](frameworks/next-auth.md) | Authentication |
| [lightweight-charts.md](frameworks/lightweight-charts.md) | Charting library |
| [z-ai-sdk.md](frameworks/z-ai-sdk.md) | AI SDK integration |
| [react-hook-form-zod.md](frameworks/react-hook-form-zod.md) | Form handling |
| [recharts.md](frameworks/recharts.md) | Recharts library |
| [pinets.md](frameworks/pinets.md) | Pinets integration |
| [README.md](frameworks/README.md) | Frameworks overview |

### 🎨 UI/UX (`ui/`)
User interface documentation.

| Document | Description |
|----------|-------------|
| [UI_REDESIGN_2026.md](ui/UI_REDESIGN_2026.md) | 2026 redesign |
| [UI_INTEGRATION.md](ui/UI_INTEGRATION.md) | UI integration |
| [UI_PHASE_IMPROVEMENTS.md](ui/UI_PHASE_IMPROVEMENTS.md) | Phase improvements |
| [UI_ADAPTATION_RECOMMENDATIONS.md](ui/UI_ADAPTATION_RECOMMENDATIONS.md) | Adaptation guide |
| [ADVANCED_ANALYTICS.md](ui/ADVANCED_ANALYTICS.md) | Analytics UI |
| [ACCESSIBILITY_GUIDE.md](ui/ACCESSIBILITY_GUIDE.md) | WCAG compliance |
| [ACCESSIBILITY_CHECKLIST.md](ui/ACCESSIBILITY_CHECKLIST.md) | Accessibility checklist |
| [COMPONENT_STORYBOOK.md](ui/COMPONENT_STORYBOOK.md) | Storybook guide |
| [THEME_CUSTOMIZATION.md](ui/THEME_CUSTOMIZATION.md) | Theme guide |
| [MOBILE_UX_GUIDE.md](ui/MOBILE_UX_GUIDE.md) | Mobile UX |
| [DESIGN_SYSTEM.md](ui/DESIGN_SYSTEM.md) | Design system |

### 🧩 UI Components (`components/`)
User interface component documentation.

| Document | Description |
|----------|-------------|
| [README.md](components/README.md) | Components overview |
| [DASHBOARD.md](components/DASHBOARD.md) | Dashboard widgets (14 components) |
| [CHART.md](components/CHART.md) | Chart components (6 components) |
| [PORTFOLIO_MANAGEMENT.md](components/PORTFOLIO_MANAGEMENT.md) | Portfolio management |
| [TRADING_SYSTEM.md](components/TRADING_SYSTEM.md) | Trading system & modes |
| [COPY_TRADING_PANEL.md](components/COPY_TRADING_PANEL.md) | Copy trading UI |
| [RISK_MANAGEMENT_UI.md](components/RISK_MANAGEMENT_UI.md) | Risk management panels |
| [OPERATIONAL_BOTS.md](components/OPERATIONAL_BOTS.md) | MESH, SCALE, BAND bots |
| [ANALYTICAL_BOTS.md](components/ANALYTICAL_BOTS.md) | PND, TRND, FCST, RNG, WOLF bots |
| [FREQUENCY_BOTS_UI.md](components/FREQUENCY_BOTS_UI.md) | HFT, MFT, LFT bots |
| [STRATEGY_LAB_HYPEROPT.md](components/STRATEGY_LAB_HYPEROPT.md) | Strategy lab & hyperopt |
| [ML_FILTERING_SYSTEM.md](components/ML_FILTERING_SYSTEM.md) | ML filtering & scoring |
| [VOLATILITY_PANEL.md](components/VOLATILITY_PANEL.md) | Volatility analysis |
| [SELF_LEARNING_PANEL.md](components/SELF_LEARNING_PANEL.md) | Genetic optimizer |
| [NOTIFICATIONS_SYSTEM.md](components/NOTIFICATIONS_SYSTEM.md) | Notifications & alerts |
| [FUNDING_RATES.md](components/FUNDING_RATES.md) | Funding rates UI |
| [ADDITIONAL_PANELS.md](components/ADDITIONAL_PANELS.md) | Journal, News, Workspace, etc. |
| [TRADING_MODES_AND_THEMES.md](components/TRADING_MODES_AND_THEMES.md) | Modes & themes |
| [RESPONSIVE_DESIGN.md](components/RESPONSIVE_DESIGN.md) | Mobile/tablet/desktop |
| [POSITIONS_TRADES_SIGNALS.md](components/POSITIONS_TRADES_SIGNALS.md) | Positions, trades, signals |
| [ANALYTICS_DASHBOARD.md](components/ANALYTICS_DASHBOARD.md) | PnL & ML analytics |
| [AI_RISK_PANEL.md](components/AI_RISK_PANEL.md) | **AI Risk Manager with anomaly detection** |
| [SHARE_FEATURES.md](components/SHARE_FEATURES.md) | **Share cards for social media** |
| [HELP_CENTER.md](components/HELP_CENTER.md) | **Help panel, FAQ, documentation** |
| [ADDITIONAL_COMPONENTS_COMPLETE.md](components/ADDITIONAL_COMPONENTS_COMPLETE.md) | **Complete component coverage** |

### 🔒 Security (`security/`)
Security documentation.

| Document | Description |
|----------|-------------|
| [SECURITY_GUIDE.md](security/SECURITY_GUIDE.md) | Security guide |
| [PENETRATION_TESTING_REPORT.md](security/PENETRATION_TESTING_REPORT.md) | Pentest report |
| [VULNERABILITY_DISCLOSURE_POLICY.md](security/VULNERABILITY_DISCLOSURE_POLICY.md) | Vulnerability policy |

### ⚙️ Backend (`backend/`)
Backend API and service documentation.

| Document | Description |
|----------|-------------|
| [README.md](backend/README.md) | Backend documentation overview |
| [BACKEND_API_REFERENCE.md](backend/BACKEND_API_REFERENCE.md) | Complete API reference (120+ endpoints) |
| [STRATEGY_ENGINE_COMPLETE.md](backend/STRATEGY_ENGINE_COMPLETE.md) | Strategy Engine (25 strategies) |
| [BOT_ENGINE_REFERENCE.md](backend/BOT_ENGINE_REFERENCE.md) | All bot engines (17+ bots) |
| [ML_SERVICES_COMPLETE.md](backend/ML_SERVICES_COMPLETE.md) | ML pipeline, RL, Deep Learning |
| [RISK_MANAGEMENT_COMPLETE.md](backend/RISK_MANAGEMENT_COMPLETE.md) | Risk management system |
| [EXCHANGE_CLIENTS_COPY_TRADING.md](backend/EXCHANGE_CLIENTS_COPY_TRADING.md) | 12 exchange clients + copy trading |
| [SIGNALS_API_COMPLETE.md](backend/SIGNALS_API_COMPLETE.md) | Signal parsing & processing |
| [AUTO_TRADING_API.md](backend/AUTO_TRADING_API.md) | Auto trading execution engine |
| [DATA_MANAGEMENT_API.md](backend/DATA_MANAGEMENT_API.md) | Backup, files, journal, news APIs |
| [CRON_JOBS_API.md](backend/CRON_JOBS_API.md) | Background jobs & workers |
| [INFRASTRUCTURE_SERVICES.md](backend/INFRASTRUCTURE_SERVICES.md) | Locks, cache, messaging, websocket |
| [INDICATORS_SERVICE_COMPLETE.md](backend/INDICATORS_SERVICE_COMPLETE.md) | **200+ индикаторов** |
| [BACKEND_COVERAGE_REPORT_100.md](backend/BACKEND_COVERAGE_REPORT_100.md) | **100% Coverage Report** |

### 📊 Indicators (`indicators/`)
Technical indicators documentation.

| Document | Description |
|----------|-------------|
| [INDICATORS_CLASSIFICATION.md](indicators/INDICATORS_CLASSIFICATION.md) | Indicator classification |

### 🔄 Migration (`migration/`)
Migration documentation.

| Document | Description |
|----------|-------------|
| [TIMESCALEDB.md](migration/TIMESCALEDB.md) | TimescaleDB migration |
| [TIMESCALEDB_MIGRATION.md](migration/TIMESCALEDB_MIGRATION.md) | Migration guide |
| [MIGRATION_TZ_MODULAR_MONOLITH.md](migration/MIGRATION_TZ_MODULAR_MONOLITH.md) | Modular monolith |

### 🗄️ Archive (`_archive/`)
Historical documents and reports.

| Directory | Description |
|-----------|-------------|
| [_archive/reports/](_archive/reports/) | Audit reports, phase reports |
| [_archive/plans/](_archive/plans/) | Historical development plans |

---

## 📋 Documentation Levels

### Level 1: Foundation (100% ✅)
- README.md, DATABASE_SCHEMA.md, API_SPECIFICATION.md
- DEPLOYMENT_GUIDE.md, ENVIRONMENT_VARIABLES.md
- FRONTEND_ARCHITECTURE.md, SECURITY_GUIDE.md, ERROR_HANDLING.md

### Level 2: Development (100% ✅)
- TESTING_STRATEGY.md, BOT_ALGORITHMS.md, CONTRIBUTING.md
- TROUBLESHOOTING.md, MONITORING_AND_ALERTING.md
- WEBSOCKET_PROTOCOL.md, ML_MODELS_DOCUMENTATION.md
- EXCHANGE_INTEGRATION_GUIDE.md, ARCHITECTURE_DECISION_RECORDS.md

### Level 3: Operations (100% ✅)
- INCIDENT_RESPONSE_PLAYBOOK.md, DISASTER_RECOVERY_PLAN.md
- CAPACITY_PLANNING.md, PERFORMANCE_TUNING.md
- WEBHOOK_INTEGRATION.md, THIRD_PARTY_INTEGRATIONS.md
- API_VERSIONING_STRATEGY.md

### Level 4: Business (100% ✅)
- USER_MANUAL.md, ADMIN_GUIDE.md
- RISK_MODELS_DOCUMENTATION.md, MARKET_DATA_SPECIFICATION.md
- ORDER_EXECUTION_LOGIC.md, AUDIT_TRAIL_SPECIFICATION.md
- COMPLIANCE_GUIDE.md, BUSINESS_REQUIREMENTS.md

### Level 5: Backend (100% ✅)
- BACKEND_API_REFERENCE.md (120+ endpoints)
- BOT_ENGINE_REFERENCE.md (17+ bots)
- ML_SERVICES_COMPLETE.md (ML/RL/DL)
- RISK_MANAGEMENT_COMPLETE.md
- EXCHANGE_CLIENTS_COPY_TRADING.md (12 exchanges)
- STRATEGY_ENGINE_COMPLETE.md (25 strategies)
- SIGNALS_API_COMPLETE.md
- AUTO_TRADING_API.md
- DATA_MANAGEMENT_API.md
- CRON_JOBS_API.md
- INFRASTRUCTURE_SERVICES.md
- INDICATORS_SERVICE_COMPLETE.md (**200+ indicators**)
- COMPONENT_INTERACTIONS.md (**All interactions**)
- BACKEND_COVERAGE_REPORT_100.md (**100% coverage**)

### Level 6: Frontend (100% ✅)
- hooks/README.md (**All 14 hooks**)
- state-management/README.md (**Complete Zustand store**)
- types/README.md (**All TypeScript interfaces**)
- components/README.md (**All UI components**)
- components/ADDITIONAL_COMPONENTS_COMPLETE.md (**15+ additional panels**)
- components/AI_RISK_PANEL.md (**AI Risk Manager**)
- components/SHARE_FEATURES.md (**Share cards**)
- components/HELP_CENTER.md (**Help panel**)
- skills/README.md (**18 AI skills**)
- examples/README.md (**WebSocket examples**)
- integrations/IAF_SERVICE.md (**IAF Python service**)
- bots/VISION_V2.md (**Vision V2 online learning**)

---

## 🔍 Quick Links

| I want to... | Go to |
|--------------|-------|
| Set up the project | [DEPLOYMENT_GUIDE.md](deployment/DEPLOYMENT_GUIDE.md) |
| Understand the API | [API_SPECIFICATION.md](architecture/API_SPECIFICATION.md) |
| View backend APIs | [BACKEND_API_REFERENCE.md](backend/BACKEND_API_REFERENCE.md) |
| Add a new exchange | [EXCHANGE_INTEGRATION_GUIDE.md](business-logic/EXCHANGE_INTEGRATION_GUIDE.md) |
| Create a new bot | [BOT_ALGORITHMS.md](business-logic/BOT_ALGORITHMS.md) |
| Configure monitoring | [MONITORING_AND_ALERTING.md](deployment/MONITORING_AND_ALERTING.md) |
| Understand risk models | [RISK_MODELS_DOCUMENTATION.md](business-logic/RISK_MODELS_DOCUMENTATION.md) |
| Handle an incident | [INCIDENT_RESPONSE_PLAYBOOK.md](deployment/INCIDENT_RESPONSE_PLAYBOOK.md) |
| Follow compliance | [COMPLIANCE_GUIDE.md](business-logic/COMPLIANCE_GUIDE.md) |
| Understand microservices | [microservices/README.md](microservices/README.md) |
| Set up ML pipeline | [ML_INTEGRATION.md](ml/ML_INTEGRATION.md) |
| Configure copy trading | [copy-trading.md](trading/copy-trading.md) |
| Use exchange clients | [EXCHANGE_CLIENTS_COPY_TRADING.md](backend/EXCHANGE_CLIENTS_COPY_TRADING.md) |
| View exchange docs | [exchanges/README.md](exchanges/README.md) |

---

## 📝 Documentation Contribution Guide

### How to Add Documentation

1. **Create the Document**
   ```bash
   # Create in appropriate directory
   touch docs/category/NEW_DOCUMENT.md
   ```

2. **Use Standard Template**
   ```markdown
   # Document Title

   **Version:** 1.0 | **Last Updated:** YYYY-MM-DD

   ---

   ## Overview

   Brief description of what this document covers.

   ## Table of Contents

   - [Section 1](#section-1)
   - [Section 2](#section-2)

   ## Section 1

   Content here...

   ## See Also

   - [Related Document](path/to/doc.md)
   ```

3. **Update docs/README.md**
   Add your document to the appropriate category table.

4. **Update Root README.md**
   If the document is significant, add a reference.

### Documentation Categories

| Category | Purpose | Directory |
|----------|---------|-----------|
| Architecture | System design | `architecture/` |
| Business Logic | Trading logic | `business-logic/` |
| Deployment | Infrastructure | `deployment/` |
| Development | Developer guides | `development/` |
| Bots | Trading bots | `bots/` |
| ML | Machine learning | `ml/` |
| Trading | Trading docs | `trading/` |
| Exchanges | Exchange docs | `exchanges/` |
| UI/UX | Interface docs | `ui/` |
| Security | Security docs | `security/` |
| Microservices | Service docs | `microservices/` |

---

## 📐 Documentation Style Guide

### Markdown Standards

| Element | Standard |
|---------|----------|
| **Headers** | ATX style (# Header) |
| **Lists** | Use `-` for unordered, `1.` for ordered |
| **Code** | Use fenced blocks with language |
| **Links** | Use relative paths for internal links |
| **Tables** | Use GFM table syntax |
| **Images** | Store in `docs/assets/` |

### Writing Guidelines

1. **Be Concise** - Get to the point quickly
2. **Use Examples** - Show code examples when possible
3. **Link to Sources** - Reference source files
4. **Keep Updated** - Update when code changes
5. **Use Diagrams** - ASCII diagrams for architecture

### Code Examples

```typescript
// Always use TypeScript for code examples
// Include imports
import { SomeClass } from '@/lib/some-class';

// Show usage
const instance = new SomeClass();
const result = instance.method();
```

### Document Structure

```
1. Title & Metadata
2. Overview
3. Table of Contents
4. Main Content
5. API Reference (if applicable)
6. Examples
7. See Also
8. Changelog (if applicable)
```

---

## 🔄 Documentation Review Process

### Review Checklist

- [ ] Document follows style guide
- [ ] All code examples are tested
- [ ] Links are valid
- [ ] Tables are formatted correctly
- [ ] Document is in correct category
- [ ] README.md is updated
- [ ] No duplicate content

### Review Stages

| Stage | Reviewer | Focus |
|-------|----------|-------|
| Technical | Tech Lead | Accuracy, completeness |
| Editorial | Doc Writer | Style, clarity |
| Final | Team Lead | Approval |

### Update Triggers

- New feature implementation
- API changes
- Bug fixes affecting behavior
- Architecture changes
- Security updates

---

## 🔎 Search & Navigation

### Finding Documentation

1. **By Category** - Use the tables above
2. **By Topic** - Use Quick Links section
3. **By File** - Browse directories directly
4. **By Keyword** - Use grep or IDE search

### Navigation Tips

```bash
# Find all API documentation
find docs -name "*.md" | xargs grep -l "API"

# Find specific topic
grep -r "VaR" docs/

# List all documents
find docs -name "*.md" | sort
```

### External Resources

| Resource | Link |
|----------|------|
| Main README | [../README.md](../README.md) |
| Changelog | [../CHANGELOG.md](../CHANGELOG.md) |
| Contributing | [development/CONTRIBUTING.md](development/CONTRIBUTING.md) |

---

## 📊 Statistics

| Metric | Value |
|--------|-------|
| Total Documents | 190+ |
| Core Documents | 100% coverage |
| Total Lines | ~60,000+ |
| Languages | TypeScript, Python, SQL, Go |
| Categories | 25 |
| Hooks Documented | 14 (100%) |
| Types Documented | 18+ interfaces (100%) |
| Store Slices Documented | 7 (100%) |
| Skills Documented | 18 (100%) |
| Bot Types Documented | 17+ (100%) |
| UI Components Documented | 170+ (100%) |

---

## 📜 Documentation Versioning

### Version Format

Documents use semantic versioning: `MAJOR.MINOR.PATCH`

| Change Type | Version Impact |
|-------------|----------------|
| Major rewrite | MAJOR |
| New sections | MINOR |
| Typos, small fixes | PATCH |

### Version Header

Each document should include:

```markdown
**Version:** 1.0.0 | **Last Updated:** YYYY-MM-DD | **Status:** Draft/Review/Approved
```

---

*Last updated: March 2026 | CITARION Documentation Team*
