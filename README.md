# Widgets

A collection of HTML widgets designed to be embedded in Notion pages.

## TradingView Chart Widget

`tradingview.html` embeds an interactive [TradingView](https://www.tradingview.com/) Advanced Chart that you can drop straight into any Notion page.

### Features

- Full-viewport, responsive chart that fills the Notion embed frame
- Dark theme by default
- Symbol search bar – switch to any stock, crypto, forex, or index on the fly
- Configurable default symbol, interval, timezone, and theme

### How to use in Notion

1. **Host the file** – upload `tradingview.html` to any static hosting service (e.g. GitHub Pages, Netlify, Vercel, or a simple web server).
2. **Copy the public URL** of the hosted file (e.g. `https://yourusername.github.io/Widgets/tradingview.html`).
3. In Notion, type `/embed` and select **Embed**.
4. Paste the URL and click **Embed link**.
5. Resize the embed block to your preferred height.

### Customisation

Open `tradingview.html` and edit the options passed to `new TradingView.widget({...})`:

| Option | Default | Description |
|--------|---------|-------------|
| `symbol` | `"NASDAQ:AAPL"` | Default ticker shown on load |
| `interval` | `"D"` | Default chart interval (`"1"` = 1 min, `"5"` = 5 min, `"15"` = 15 min, `"60"` = 1 hr, `"D"` = 1 day, `"W"` = 1 week, `"M"` = 1 month) |
| `theme` | `"dark"` | `"dark"` or `"light"` |
| `timezone` | `"Etc/UTC"` | Any TZ database name (e.g. `"America/New_York"`) |
| `allow_symbol_change` | `true` | Show the symbol search toolbar |

Full list of widget options: <https://www.tradingview.com/widget/advanced-chart/>

---

## TradingView Watchlist Widget

`watchlist.html` embeds the TradingView **Market Overview (Watchlist)** widget — a tabbed, real-time price list covering Indices, Futures, Crypto, and Forex. Perfect for a quick-glance market overview in Notion.

### Features

- Full-viewport, responsive list that fills the Notion embed frame
- Dark theme by default
- Four pre-configured tabs: **Indices**, **Futures**, **Crypto**, **Forex**
- Inline mini-chart for each symbol
- Easily customisable — add, remove, or reorder tabs and symbols

### How to use in Notion

1. **Host the file** – upload `watchlist.html` to any static hosting service (e.g. GitHub Pages, Netlify, Vercel, or a simple web server).
2. **Copy the public URL** of the hosted file (e.g. `https://yourusername.github.io/Widgets/watchlist.html`).
3. In Notion, type `/embed` and select **Embed**.
4. Paste the URL and click **Embed link**.
5. Resize the embed block to your preferred height.

### Customisation

Open `watchlist.html` and edit the JSON configuration passed inside the `<script>` tag:

| Option | Default | Description |
|--------|---------|-------------|
| `colorTheme` | `"dark"` | `"dark"` or `"light"` |
| `dateRange` | `"12M"` | Sparkline range: `"1D"`, `"1M"`, `"3M"`, `"12M"`, `"60M"`, `"ALL"` |
| `showChart` | `true` | Show the mini sparkline chart next to each symbol |
| `showSymbolLogo` | `true` | Show exchange/asset logo icons |
| `tabs` | *(see file)* | Array of tab objects — each has a `title` and a `symbols` array |

To add a symbol, append an entry to any tab's `symbols` array:
```json
{"s": "NASDAQ:MSFT", "d": "Microsoft"}
```

Full list of widget options: <https://www.tradingview.com/widget/market-overview/>
