# aoi.

A private, multi-currency cashflow ledger that lives on your phone.

**Live app:** [olavism.github.io/aoi](https://olavism.github.io/aoi/)

## Purpose

aoi started life as a Google Sheets budget tracker and grew into a proper app. It's built for freelancers and anyone whose money moves in more than one currency: client retainers in USD or GBP, daily expenses in PHP, a little crypto on the side. It answers the questions a spreadsheet answers — what came in, what went out, what's still due, what's pending — but in something you can open with one tap and use with one thumb.

It is deliberately **not** a fintech product. There are no accounts, no sign-ups, no servers, and no analytics. Your financial data never leaves your device.

## Features

- **Overview dashboard** — income, expenses, net, pending, and investments at a glance, with month-over-month comparison, a yearly cashflow chart, and category/client breakdowns
- **Multi-currency ledger** — record transactions in any currency; live exchange rates (ER-API for fiat, CoinGecko for crypto and gold) convert everything to your base currency, while past entries keep their historical rates
- **Status workflow** — income is *Received* or *Incoming*, expenses are *Paid* or *Due*; flip a status with a tap or an Apple Mail-style swipe
- **Recurring transactions** — monthly entries roll forward automatically
- **Investments** — track crypto and gold holdings; BTC, ETH, USDT, XAU and others revalue automatically
- **Year scope** — view any year or all time; the app grows with you indefinitely
- **Privacy blur** — one tap hides every amount from shoulder surfers
- **Offline-first PWA** — installs to the home screen, works with no connection, syncs rates when back online
- **Cross-device sync (optional)** — sign in with an email code and your ledger stays identical on phone and computer; end-to-end encrypted with a passphrase, so the sync server only ever stores ciphertext
- **Backup & restore** — export your entire ledger as JSON, restore it on any device

## Install (iPhone)

1. Open [olavism.github.io/aoi](https://olavism.github.io/aoi/) in Safari
2. Tap **Share → Add to Home Screen**
3. Launch from the icon and choose *Start fresh*, *Explore with sample data*, or *Restore a backup*

Works the same on Android (Chrome → Install app) and desktop browsers.

## Privacy

All data is stored in your browser's local storage on your own device. Your financial data is never transmitted anywhere except two anonymous, read-only rate lookups (exchange rates and crypto prices). Deleting the app deletes the data, so export a backup now and then — the app reminds you.

The app sends one anonymous visit ping when opened (at most hourly): a timestamp plus two booleans (first visit or returning, installed or in-browser). No IP addresses, identifiers, or usage details are stored, and the counter is write-only to the public — it exists solely so the author knows roughly how many people use the app.

If you opt into sync, your ledger is encrypted on-device (AES-GCM, key derived from your passphrase via PBKDF2) before upload; the backend stores only ciphertext it cannot read, protected by row-level security. The passphrase never leaves your devices — and that means it's unrecoverable if forgotten, so don't forget it.

## Tech

A single self-contained `index.html` — no framework, no build step, no dependencies. Plus a service worker for offline support, a web app manifest, and icons. Hosted free on GitHub Pages.

## License

MIT — use it, fork it, share it.
