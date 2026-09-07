# Price in Hours

A single-file web app that converts a dollar price into the hours of *surplus*
work it costs — the money left after tax and fixed obligations, not gross pay.

Buying something discretionary is not paid for out of your wage. It comes out
of what survives tax, housing, insurance, debt and everything else already
promised. That bucket is much smaller than a paycheck and fills far more
slowly, which is why a $1,100 phone can cost well over a hundred hours.

## Features

- **2026 federal tax model** — full bracket table for single, married-joint and
  head-of-household filers, the standard deduction, FICA with the Social
  Security wage base and the additional Medicare surtax.
- **1099 contractor mode** — self-employment tax at 15.3% on 92.35% of net
  profit, the deductible half, the 20% QBI deduction, deductible business
  expenses, and a quarterly tax-reserve figure.
- **Fixed obligations ledger** — ten expense categories, monthly or yearly,
  each priced in hours per month.
- **Additive hours** — every line is measured against the gross hourly rate, so
  tax + deductions + fixed costs + surplus add back up to the hours worked.
- **Break-even date** — the day in the year the bills are covered and earnings
  start being yours.
- Collapsible setup, light and dark themes, and per-visitor `localStorage`.

## Running it

Open `index.html` in a browser. There is no build step and no backend. The only
external request is to Google Fonts; without it the page falls back to system
fonts. Everything entered stays in that browser and is never transmitted.

## Accuracy

A planning estimate, not a tax return. It ignores itemized deductions, credits,
other household income and local tax. The QBI deduction is modelled below the
phase-in threshold and flagged above it, where W-2 wage limits and
specified-service rules apply. Check anything that matters with a CPA.

Tax figures follow IRS Rev. Proc. 2025-32 and the SSA 2026 wage base. To update
for a later year, edit the `FILING` object, `SS_WAGE_BASE` and `TAX_YEAR` near
the top of the script — nothing else depends on them.
