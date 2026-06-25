# help-paymentops-report

Weekly operational report for the #help-paymentops channel (Cards & Payments Ops), in the Jeeves report layout — the Payments Ops counterpart to the Disputes report.

Hosted with GitHub Pages at: `https://fernandah-tryjeeves.github.io/help-paymentops-report/`

## Structure
- `index.html` — the latest/current report (this is what the email button links to)
- `reports/` — archived reports by week, named `YYYY-MM-DD.html` (Monday of the week). The "📅 Reports" dropdown in the page reads this folder via the GitHub API.
- `.nojekyll` — tells GitHub Pages to serve files as-is.

## Before it works: one manual step
Open `index.html` AND `reports/2026-06-22.html` and replace:

```js
const CLIENT_ID = 'PASTE_GOOGLE_CLIENT_ID_HERE';
```

with the same Google OAuth Client ID used by the disputes-report repo (copy it from `disputes-report/index.html` — it's the same @tryjeeves.com OAuth client). Without it the Google sign-in button won't render.

> Tip: if you want to test locally before hosting, the sign-in only fires when served from the Pages domain registered in the OAuth client. Opening the file directly will sit on the login screen — that's expected.

## Publishing a new week
1. Copy the new report HTML into `reports/2026-MM-DD.html` (Monday of that week).
2. In that file set `const CURRENT_REPORT_FILENAME = '2026-MM-DD.html';`
3. Replace `index.html` with the same content but `CURRENT_REPORT_FILENAME = ''`.
4. Commit + push. The dropdown picks up the new file automatically.
