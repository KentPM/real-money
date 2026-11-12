# Real Money v0.4 — GitHub Pages PWA

Static offline-first budgeting app. No server or build step.

## Deploy
1. Upload **the files inside this ZIP** (not the ZIP itself) to the repository root on `main`.
2. In repository **Settings → Pages**, choose **Deploy from a branch**, `main`, `/ (root)` and save.
3. Visit https://kentpm.github.io/real-money/ in Chrome on Android, then use **⋮ → Add to Home screen / Install app**.

## Privacy and data
Only upload application files, **never JSON backups or transaction data**. Data is stored in this browser's localStorage and does not synchronize between devices. Before migrating from a local file, export JSON from the old app and import it into the new hosted app. Keep backup copies.

## Updates
Replace files in the repository. When updating the service worker's cache version, increment `CACHE` to ensure old cached assets are retired.

## Forecasting
Planned income and expenses change projected balances on their scheduled dates. Cleared entries are already included in your bank balance. A manual entry replaces one recurring occurrence when date, type, amount (to the cent), and description (ignoring case and outer whitespace) match; explicit recurring links take priority. Use a distinct description for genuinely separate, otherwise identical payments.

Safe to Spend excludes future income and subtracts expenses through the next income date (including that day's expenses) plus your buffer. If no income is scheduled, it uses 60 days of expenses. Changing the chart range does not change this allowance. Chart details show each day's closing balance, income, expenses, and item count.

Quick Reconcile preserves history and clears only entries dated today or earlier when selected. Leave clearing unchecked to retain pending entries. Existing storage and JSON backups remain compatible.

## Validation
Run `node tests/forecast.cjs` with Playwright and Chromium available in your development environment. The app itself has no external dependencies.
