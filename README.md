# SENTINEL Mobile Scanner v1

A mobile-first Progressive Web App (PWA) starter for Android. It scans BTC, ETH, SOL, DOGE and XRP USD hourly candles using Coinbase's public market-data endpoint. No API key or exchange account is required.

## What it does
- Fetches public hourly candles when opened and when Scan Again is tapped.
- Calculates EMA 20, EMA 50, RSI 14 and relative volume.
- Displays rule-based BUY WATCH / SELL WATCH / HOLD labels and explanations.
- Caches the app shell for quicker reloads.

## Important limitations
- Signals are educational watchlist prompts, not financial advice or trade recommendations.
- No order placement, wallet connection, exchange credentials, push notifications or 24/7 background scanning.
- A PWA needs to be hosted over HTTPS to install reliably on Android. The browser may limit background activity; this version scans while open / on manual refresh.
- Public API availability, rate limits and browser connectivity can vary.

## Deploy free with GitHub Pages
1. Create a GitHub account and a new public repository named `sentinel-mobile-scanner`.
2. Upload all files in this folder to the repository root.
3. In repository Settings > Pages, choose Deploy from a branch, select `main` and `/ (root)`, then Save.
4. Wait for GitHub Pages to publish the HTTPS site.
5. On Android, open the published URL in Chrome. Tap the three-dot menu > Install app (or Add to Home screen) > Install.

## Run locally for development
Serve this folder with any local static HTTP server. Service workers and PWA installation require HTTPS or localhost.

## Technical notes
Market data uses Coinbase Advanced Trade public candles:
`https://api.coinbase.com/api/v3/brokerage/market/products/{product_id}/candles`
with `granularity=ONE_HOUR`. No authenticated endpoints are used.
