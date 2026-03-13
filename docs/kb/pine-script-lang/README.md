# Pine Script v6 Knowledge Base

Полная база знаний по языку программирования Pine Script v6 для TradingView.

## 📊 Статистика

| Метрика | Значение |
|---------|----------|
| **Статей** | 72 |
| **Code blocks** | 1,166 |
| **Изображений** | 827 |
| **Размер** | ~5 MB |

## 📁 Структура

```
Pine_Script_KB/
├── Language/           # Основы языка (16 статей)
│   ├── Arrays.md
│   ├── Maps.md
│   ├── Matrices.md
│   ├── Methods.md
│   ├── Objects.md
│   ├── Enums.md
│   ├── Functions.md
│   └── ...
├── Visuals/            # Визуализация (11 статей)
│   ├── Plots.md
│   ├── Tables.md
│   ├── Colors.md
│   └── ...
├── Concepts/           # Концепции (13 статей)
│   ├── Strategies.md
│   ├── Alerts.md
│   ├── Sessions.md
│   └── ...
├── Writing/            # Написание скриптов (5 статей)
├── Errors/             # Ошибки (4 статьи)
├── FAQ/                # Частые вопросы (13 статей)
├── Migration/          # Миграция v2→v6 (6 статей)
└── Release/            # Release notes
```

## 💻 Пример кода

```pine
//@version=6
indicator("Array Example", overlay = true)

// Создание массива
var prices = array.new<float>(0)
array.push(prices, close)

// Вывод размера на последнем баре
if barstate.islast
    label.new(bar_index, high, "Size: " + str.tostring(array.size(prices)))
```

## 🔗 Источник

- **Официальная документация:** https://www.tradingview.com/pine-script-docs/
- **Pine Script Reference:** https://www.tradingview.com/pine-script-reference/v6/

---

*Создано: 2025-03-05*
*Версия Pine Script: v6*
