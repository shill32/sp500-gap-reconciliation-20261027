# S&P 500 gap reconciliation (1996+, free sources only)

Labeled evidence for historical index-membership vs price/return coverage. **Not CRSP/WRDS/Norgate. Not backtest-ready.**

Start here: [`integrated/summary.json`](integrated/summary.json)

## What this is

- Conflict audit of 57 quarantined annual-return disagreements: **43 resolved, 14 unresolved**
- Extra issuer-table calendar years (Enron/WaMu/WorldCom, plus conflict supplements)
- Qualified AABA = Yahoo common stock, 2009–2016 (same shares / CUSIP change; no cash dividends as of 2016 10-K; graph has no numeric table)
- Span-level coverage flags for the Downloads `gap_inventory.csv` rows

## What this is not

- No PERMNO / CRSP / Norgate membership+returns
- No delisting cashflows (2001 Enron, 2008 Lehman/WaMu, etc.)
- No historical shares outstanding / market caps for weighting
- Untrimmed Yahoo-compiled daily archives (364 files) are **not** in this repo (identity unverified; ~100MB+)
- 6,077 unverified archive annual candidates are **not** included as coverage
- Original backtest inputs were **not** changed

## Key files

| Path | Contents |
|---|---|
| `integrated/conflict_resolutions.csv` | All 57 conflicts |
| `integrated/issuer_primary_extra_years.csv` | Extra issuer calendar years |
| `integrated/aaba_yahoo_qualified_returns.csv` | Same-share Yahoo→Altaba |
| `integrated/span_coverage_after_resolution.csv` | Per membership span |
| `primary/bankrupt/annual_returns.csv` | ENRNQ 1995–2000, WAMUQ 1996–2000, WCOM 1996/98/99 |
| `primary/bankrupt/lehman_fiscal_november_returns.csv` | LEHMQ **fiscal November**, not calendar |
| `quick_scour/return_conflicts_quarantine.csv` | Original 57-row conflict list |
| `conflict_resolution/{identity,dividends,remaining}/` | Group-level resolutions |

## Hard limits (do not ignore)

- LSI archive tape = Life Storage, not LSI Corporation
- AGN archive tape = Actavis / Allergan plc, not original Allergan Inc
- Current `WM` is not Washington Mutual; WaMu maps to **WAMUQ**
- WorldCom 1997 withheld (DEF14A tables disagree); WorldCom is **not** inventory `MCIC`
- IGT / GPS / VAR issuer tables are **fiscal**, not calendar
- Lehman DEF14A TSR is **fiscal November**

Date: 2026-10-27
