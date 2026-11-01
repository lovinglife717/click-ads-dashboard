# Click Ads Dashboard — development build v0.1

## Cost
No required paid libraries, database, subscriptions, APIs, or server. Source is static HTML/CSS/JavaScript. User financial data is saved locally in browser IndexedDB, not uploaded to a server.

## Run
Use a local HTTP server for development: `python3 -m http.server 8000` from this directory, then open `http://localhost:8000` on your computer. For iPhone Safari and Add to Home Screen, deploy these static files to an HTTPS host with a free plan (for example GitHub Pages); verify the provider's current free-tier terms. Do **not** just open `index.html` in the iPhone Files preview, which may not provide durable IndexedDB or service-worker support. Installing on the Home Screen requires a supported secure origin. The app can work offline after first loading and caching from HTTPS.

## Data and privacy
Only the application code is hosted. Financial data stays on the device in IndexedDB. iOS may clear website data; use Settings > Save backup JSON frequently and keep the backups in iPhone Files. A browser or Home Screen app storage context can differ: verify storage persistence before entering important records. No PIN is included, per the user's chosen security setting. No credentials should be entered into this app.

## Implemented in v0.1
- Dark mobile dashboard with Home, Campaigns, Finances, Planner, Settings.
- Seven-level user-provided reference table, six-decimal integer USDT math, two-decimal display.
- Create purchased campaigns with once-per-level activation fee and conservative funding check.
- Mark daily clicks; backdate click confirmations; mark 12-day completion and six-day hold.
- Three clicking-slot maximum; unlimited holds.
- Manually confirm full or partial payout and credit confirmed amount once.
- Record personal deposits (gross/fee/net), completed withdrawals, and balance adjustments.
- Calculate cash P/L and platform gains separately.
- Verify platform balance; use lower of verified and calculated balance for affordability.
- Plan campaigns, reserve confirmed funds, postpone/resume, release/cancel and confirm actual purchase.
- JSON backup and restore with a safety-backup prompt, exact CSV transaction export, audit log.

## Not implemented yet
This is not a complete implementation of all approved Steps 1–195. Outstanding items include robust transaction correction and deletion, richer reservation splitting/merging/transfers, complete scenario/risk simulation, calendar export, reminder scheduling, configurable reference table UI, PDF reports, detailed charts, restore conflict reconciliation and fully atomic restore guarantees, all historical edge cases, comprehensive testing, and iPhone deployment. Do not rely on the prototype as the sole source of financial truth.

## Safety
The platform's expected payout numbers are unverified user-provided reference values. This app cannot verify platform legitimacy, ensure payouts, or initiate purchases. Do not enter wallet secrets, private keys, or passwords.
