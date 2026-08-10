# S&P 500 vs. the Biggest Company vs. Funds vs. the Mag 7 — Backtest

A self-contained, interactive backtest comparing eight strategies for $100,000 invested on
the first trading day of 2020 and held through 2026-08-07, with taxes and fees modeled explicitly.

**Live:** deployed on Vercel (see the deployment URL).

## Strategies
- **A — S&P 500 (SPY)**, plus its index-fund twin **VFIAX** and an actively-managed fund **AGTHX**
  chosen by a hindsight-free rule (largest active US equity fund by AUM as of Jan 2020).
- **B1 — static:** buy the 2020 market-cap leader (Apple) and hold untouched.
- **B2 — rebalance:** hold whichever company is currently #1, switching on documented leadership changes.
- **MSFT control:** the largest company in 2020 that was *not* Apple (same rule, different draw).
- **Magnificent 7:** equal-weight, held static or rebalanced annually.

## Methodology
- **Data:** Yahoo Finance daily closes. Returns are **total return** (dividends reinvested, split-adjusted);
  a price-return toggle is included.
- **Taxes:** single federal filer, long-term 15% / short-term 24% (adjustable in the UI), federal only.
- **Fees:** fund values are NAV net of expense ratio; each fund's cumulative fee cost is shown separately.
- **Selection bias is treated explicitly** — every strategy except the index was chosen knowing the outcome,
  and the artifact says so, with an SPIVA comparison and a non-Apple control.
- Every fund ticker, expense ratio, and constituent is verified against a cited source. Not predictive.
  Not financial advice.

## Run locally
Just open `index.html` in a browser (loads Chart.js from a CDN). No build step.
