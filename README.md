# Real Money v0.3 — GitHub Pages PWA

Static offline-first budgeting app. No server or build step.

## Deploy
1. Upload **the files inside this ZIP** (not the ZIP itself) to the repository root on `main`.
2. In repository **Settings → Pages**, choose **Deploy from a branch**, `main`, `/ (root)` and save.
3. Visit https://kentpm.github.io/real-money/ in Chrome on Android, then use **⋮ → Add to Home screen / Install app**.

## Privacy and data
Only upload application files, **never JSON backups or transaction data**. Data is stored in this browser's localStorage and does not synchronize between devices. Before migrating from a local file, export JSON from the old app and import it into the new hosted app. Keep backup copies.

## Updates
Replace files in the repository. When updating the service worker's cache version, increment `CACHE` to ensure old cached assets are retired.
