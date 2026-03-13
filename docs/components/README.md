# CITARION UI Components

**Version:** 2.0 | **Last Updated:** March 2026

---

## 📋 Overview

This document provides an overview of all UI components used in CITARION, built with shadcn/ui and customized for trading interfaces.

---

## 🧩 Component Categories

### Core Components (40+)

Located in `src/components/ui/`:

| Component | Description | Usage |
|-----------|-------------|-------|
| `Button` | Primary action buttons | Trading actions, form submissions |
| `Input` | Text and number inputs | Order forms, search |
| `Select` | Dropdown selections | Symbol picker, exchange selector |
| `Dialog` | Modal dialogs | Confirmations, settings |
| `Sheet` | Side panel drawers | Quick actions, filters |
| `Table` | Data tables | Positions, trades, orders |
| `Card` | Container cards | Dashboard widgets |
| `Tabs` | Tab navigation | Market views, analysis |
| `Toast` | Notifications | Success/error messages |
| `Badge` | Status indicators | Position status, bot state |
| `Avatar` | User avatars | Profile display |
| `Progress` | Progress bars | Loading states |
| `Skeleton` | Loading placeholders | Content loading |
| `Tooltip` | Hover tooltips | Information hints |
| `Popover` | Popup content | Quick actions |
| `Command` | Command palette | Quick navigation |
| `Calendar` | Date picker | Date range selection |
| `Chart` | Data visualization | Price charts, analytics |

---

## 📊 Trading-Specific Components

### Order Form Components

```tsx
// Located in src/components/trading/
├── OrderForm.tsx          // Main order entry
├── OrderTypeSelector.tsx  // Market/Limit/Stop
├── LeverageSlider.tsx     // Leverage control
├── PositionSizeInput.tsx  // Size with % buttons
├── PriceInput.tsx         // Price with validation
├── TakeProfitInput.tsx    // TP levels
├── StopLossInput.tsx      // SL configuration
└── OrderPreview.tsx       // Order summary
```

### Position Components

```tsx
// Located in src/components/positions/
├── PositionCard.tsx       // Single position display
├── PositionList.tsx       // List of positions
├── PositionTable.tsx      // Table view
├── ClosePositionButton.tsx// Close action
├── PositionPnL.tsx        // P&L display
└── TrailingStopConfig.tsx // Trailing stop setup
```

### Bot Components

```tsx
// Located in src/components/bots/
├── BotCard.tsx            // Bot status card
├── BotList.tsx            // List of bots
├── BotConfigForm.tsx      // Configuration form
├── BotMetrics.tsx         // Performance metrics
├── BotLogs.tsx            // Activity log
└── BotControls.tsx        // Start/Stop/Edit
```

### Chart Components

```tsx
// Located in src/components/chart/
├── PriceChart.tsx         // Main price chart
├── VolumeChart.tsx        // Volume bars
├── IndicatorOverlay.tsx   // Indicators on chart
├── DrawingTools.tsx       // Drawing tools
├── TimeframeSelector.tsx  // Timeframe switcher
└── ChartSettings.tsx      // Chart preferences
```

---

## 🎨 Component Usage Examples

### Button Variants

```tsx
import { Button } from '@/components/ui/button';

// Primary action
<Button variant="default">Buy</Button>

// Secondary action
<Button variant="secondary">Cancel</Button>

// Destructive action
<Button variant="destructive">Close Position</Button>

// Outline style
<Button variant="outline">View Details</Button>

// Ghost (no background)
<Button variant="ghost">Settings</Button>

// Icon button
<Button size="icon">
  <RefreshCw className="h-4 w-4" />
</Button>
```

### Form Components

```tsx
import { Input } from '@/components/ui/input';
import { Label } from '@/components/ui/label';
import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from '@/components/ui/select';

<div className="grid gap-4">
  <div className="grid gap-2">
    <Label htmlFor="symbol">Symbol</Label>
    <Select value={symbol} onValueChange={setSymbol}>
      <SelectTrigger>
        <SelectValue placeholder="Select symbol" />
      </SelectTrigger>
      <SelectContent>
        <SelectItem value="BTCUSDT">BTC/USDT</SelectItem>
        <SelectItem value="ETHUSDT">ETH/USDT</SelectItem>
      </SelectContent>
    </Select>
  </div>
  
  <div className="grid gap-2">
    <Label htmlFor="quantity">Quantity</Label>
    <Input
      id="quantity"
      type="number"
      value={quantity}
      onChange={(e) => setQuantity(e.target.value)}
    />
  </div>
</div>
```

### Data Table

```tsx
import { DataTable } from '@/components/ui/data-table';
import { ColumnDef } from '@tanstack/react-table';

const columns: ColumnDef<Position>[] = [
  {
    accessorKey: 'symbol',
    header: 'Symbol',
  },
  {
    accessorKey: 'side',
    header: 'Side',
    cell: ({ row }) => (
      <Badge variant={row.original.side === 'LONG' ? 'success' : 'destructive'}>
        {row.original.side}
      </Badge>
    ),
  },
  {
    accessorKey: 'size',
    header: 'Size',
  },
  {
    accessorKey: 'pnl',
    header: 'P&L',
    cell: ({ row }) => (
      <span className={row.original.pnl >= 0 ? 'text-green-500' : 'text-red-500'}>
        {formatPnL(row.original.pnl)}
      </span>
    ),
  },
];

<DataTable columns={columns} data={positions} />
```

### Dialog

```tsx
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
} from '@/components/ui/dialog';

<Dialog open={isOpen} onOpenChange={setIsOpen}>
  <DialogContent>
    <DialogHeader>
      <DialogTitle>Confirm Order</DialogTitle>
      <DialogDescription>
        You are about to place a buy order for 0.001 BTCUSDT.
      </DialogDescription>
    </DialogHeader>
    <div className="py-4">
      {/* Order details */}
    </div>
    <DialogFooter>
      <Button variant="outline" onClick={() => setIsOpen(false)}>
        Cancel
      </Button>
      <Button onClick={handleConfirm}>Confirm</Button>
    </DialogFooter>
  </DialogContent>
</Dialog>
```

### Toast Notifications

```tsx
import { useToast } from '@/components/ui/use-toast';

const { toast } = useToast();

// Success
toast({
  title: 'Order Placed',
  description: 'Buy 0.001 BTCUSDT @ $67,000',
});

// Error
toast({
  variant: 'destructive',
  title: 'Order Failed',
  description: 'Insufficient balance',
});

// With action
toast({
  title: 'Position Closed',
  description: 'Profit: +$125.50',
  action: <ToastAction altText="View">View</ToastAction>,
});
```

---

## 🔧 Custom Components

### Price Ticker

```tsx
<PriceTicker
  symbol="BTCUSDT"
  price={67000.50}
  change={2.5}
  volume={1234567890}
/>
```

### Position Card

```tsx
<PositionCard
  position={{
    id: 'pos-1',
    symbol: 'BTCUSDT',
    side: 'LONG',
    size: 0.001,
    entryPrice: 67000,
    currentPrice: 67500,
    pnl: 0.50,
    pnlPercent: 0.75,
  }}
  onClose={() => closePosition('pos-1')}
/>
```

### Bot Status Card

```tsx
<BotStatusCard
  bot={{
    id: 'grid-1',
    type: 'GRID',
    status: 'RUNNING',
    symbol: 'BTCUSDT',
    pnl: 150.25,
    uptime: '5d 12h 30m',
  }}
  onStart={() => startBot('grid-1')}
  onStop={() => stopBot('grid-1')}
  onEdit={() => editBot('grid-1')}
/>
```

---

## 📱 Responsive Components

### Mobile Bottom Sheet

```tsx
import { Sheet, SheetContent, SheetTrigger } from '@/components/ui/sheet';

<Sheet>
  <SheetTrigger asChild>
    <Button variant="ghost" size="icon" className="md:hidden">
      <Menu className="h-5 w-5" />
    </Button>
  </SheetTrigger>
  <SheetContent side="bottom" className="h-[80vh]">
    {/* Mobile navigation */}
  </SheetContent>
</Sheet>
```

### Responsive Table

```tsx
// Desktop: Table view
// Mobile: Card list

<div className="hidden md:block">
  <DataTable columns={columns} data={data} />
</div>

<div className="md:hidden space-y-4">
  {data.map((item) => (
    <MobileCard key={item.id} data={item} />
  ))}
</div>
```

---

## 🎨 Theming

All components support theming via CSS variables:

```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
  --primary: 221.2 83.2% 53.3%;
  --secondary: 210 40% 96.1%;
  --destructive: 0 84.2% 60.2%;
  --success: 142.1 76.2% 36.3%;
}

.dark {
  --background: 222.2 84% 4.9%;
  --foreground: 210 40% 98%;
  --primary: 217.2 91.2% 59.8%;
  --secondary: 217.2 32.6% 17.5%;
  --destructive: 0 62.8% 30.6%;
  --success: 142.1 70.6% 45.3%;
}
```

---

## 📚 Related Documentation

- [../frameworks/shadcn-ui.md](../frameworks/shadcn-ui.md) - shadcn/ui integration
- [DESIGN_SYSTEM.md](DESIGN_SYSTEM.md) - Design tokens
- [COMPONENT_STORYBOOK.md](COMPONENT_STORYBOOK.md) - Component documentation
- [THEME_CUSTOMIZATION.md](THEME_CUSTOMIZATION.md) - Theming guide

---

*Last updated: March 2026 | CITARION Documentation Team*
