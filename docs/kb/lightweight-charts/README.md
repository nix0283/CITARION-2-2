# Lightweight Charts Knowledge Base

A comprehensive knowledge base of [Lightweight Charts](https://tradingview.github.io/lightweight-charts/) documentation with image descriptions for all visualizations.

## Structure

```
Lightweight_Charts_KB/
├── docs/                          # Main documentation
│   ├── api/                       # API Reference
│   │   ├── enumerations/          # Enums (CrosshairMode, ColorType, LineStyle, etc.)
│   │   ├── interfaces/            # Interfaces (IChartApi, ISeriesApi)
│   │   ├── functions/             # Functions (createChart)
│   │   └── type-aliases/          # Type aliases (Time, SeriesType)
│   ├── series-types/              # Series types (Area, Bar, Baseline, Candlestick, Histogram, Line)
│   ├── chart-types/               # Chart types (Time-based, Price-based)
│   ├── price-scale/               # Price scale documentation
│   ├── panes/                     # Panes documentation
│   ├── time-zones/                # Time zones handling
│   ├── plugins/                   # Plugins system
│   │   ├── series-primitives/     # Series primitives
│   │   ├── custom_series/         # Custom series creation
│   │   ├── canvas-rendering-target/
│   │   └── pixel-perfect-rendering/
│   │       └── widths/            # Rendering widths (candlestick, columns, crosshair, full-bar)
│   ├── migrations/                # Migration guides
│   │   ├── from-v2-to-v3.md
│   │   ├── from-v3-to-v4.md
│   │   └── from-v4-to-v5.md
│   ├── android/                   # Android wrapper documentation
│   └── ios/                       # iOS wrapper documentation
├── tutorials/                     # Tutorials
│   ├── customization/             # Chart customization (10 articles)
│   ├── a11y/                      # Accessibility (5 articles)
│   ├── react/                     # React integration (2 articles)
│   ├── vuejs/                     # Vue.js integration
│   ├── webcomponents/             # Web Components integration
│   ├── how_to/                    # How-to guides (11 articles)
│   ├── demos/                     # Demo examples (9 articles)
│   └── analysis-indicators/       # Analysis indicators
├── indicator-examples/            # Technical indicators (11 indicators with code)
└── screenshots/                   # Captured chart screenshots
    └── demos/                     # Demo screenshots
```

## Contents

### Documentation (docs/)
- **75 markdown files** with comprehensive documentation
- All interactive chart visualizations captured and described
- Image descriptions for accessibility and understanding

### Tutorials
- **Customization**: Progressive chart customization from basic to advanced
- **Accessibility (a11y)**: Keyboard navigation, screen readers, readability
- **React/Vue/WebComponents**: Framework integration guides
- **How-to**: Practical implementation guides (tooltips, legends, panes, etc.)
- **Demos**: Real-world examples (moving average, real-time updates, etc.)

### Indicator Examples
11 technical indicators with complete code:
1. Average Price
2. Correlation
3. Median Price
4. Momentum
5. Moving Average
6. Percent Change
7. Product
8. Ratio
9. Spread
10. Sum
11. Weighted Close

## Image Descriptions

All chart visualizations include detailed descriptions covering:
- Chart type and purpose
- Color schemes (with hex codes where applicable)
- Axes labels and values
- Grid lines and visual elements
- Special features and annotations

## Source

Documentation extracted from: https://tradingview.github.io/lightweight-charts/

## Version

Lightweight Charts Version: 5.1

---

*This knowledge base was created for AI-assisted development and documentation purposes.*
