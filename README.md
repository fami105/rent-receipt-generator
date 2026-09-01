# Rent Receipt Generator

A single-page web app for generating, saving, and printing rent payment receipts. No backend, no build step — it's one self-contained `index.html` file.

## Features

- Fill in landlord, tenant, flat, period, amount, and payment method to build a receipt
- Live receipt preview as you type, with amount automatically spelled out in words
- Save receipts to a running history, grouped by rent period (month/year)
- Landlord & tenant directory — save flat numbers once and auto-fill the tenant/address on future receipts
- Download any single receipt, or all receipts for a given month, as a print-ready PDF (Landlord's Copy + Tenant's Copy side by side, up to 3 tenants per page)
- Tenants and receipts are sorted in natural flat-number order (1A, 1B, 2A ... 9B, 10A)
- Backup & restore everything (receipts, directory, receipt-number counter) as a downloadable JSON file

## Usage

Just open `index.html` in a browser — no installation or server required.

### Hosting on GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to "Deploy from a branch", pick your default branch and the `/ (root)` folder.
4. Save. GitHub will publish the app at `https://<your-username>.github.io/<repo-name>/`.

## Data storage

The app uses the `window.storage` API for the receipts, directory, and receipt-number counter, so your data persists in the browser between visits. Use **Backup & restore** in the app periodically to export a JSON copy — this is your safety net if you clear browser data, switch browsers, or move to a new device.

## Tech notes

- Plain HTML/CSS/JS, no framework or build tooling
- PDF generation uses [jsPDF](https://github.com/parallax/jsPDF) (loaded from a CDN), drawing each receipt directly as vector text/shapes — no print dialog or intermediate file needed
