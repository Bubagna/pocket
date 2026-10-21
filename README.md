# Pocket

A pocket-sized expense tracker for iPhone, installed from the browser.

Add what you spent, in **CHF, EUR or USD**, say **which account paid** (yours or your parents'
card) and **what it was for**. Pocket shows each month: the total, how it splits between
accounts, a ranked list of categories, and every expense day by day. The **Trend** tab
compares the last 12 months. The currency switch at the top converts everything.

## Install it

Open the page in Safari on iPhone, then **Share → Add to Home Screen**. After the first load a
service worker keeps the app on the phone, so it opens with no network.

## Exchange rates

Rates come from the European Central Bank through [Frankfurter](https://frankfurter.dev), no key
needed. Each expense keeps the rates **of its own day**, so last month's total does not move when
the franc does. An expense entered offline gets provisional rates and is corrected the next time
the app is online.

## What it stores

Everything lives in `localStorage` on the phone; nothing is uploaded. Settings → Backup exports
JSON (to restore or move phones) and CSV (for Excel). Import merges, it never deletes.

## Hacking on it

One file, no dependencies, no build step: `index.html`. Bump `BUILD` in `index.html` and `CACHE`
in `sw.js` whenever a file changes, or phones keep the old copy.
