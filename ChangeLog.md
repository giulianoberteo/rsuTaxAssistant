# Changelog

All notable changes to the RSU Tax Calculator are recorded here.

Format: `[version] YYYY-MM-DD — summary`

---

## [1.3.0] 2026-06-19 — GBP equivalent in Tax Summary

### Added
- "GBP Rate (1 USD =)" input in the controls bar (default 0.787); updates live
- Every monetary Tax Summary card now shows the GBP equivalent below the USD value, separated by a dashed divider
- `fmtGBP()` helper converts any USD amount using the live exchange rate

---

## [1.2.0] 2026-06-19 — Readability improvements

### Changed
- Data rows: padding increased from 6px to 10px (taller rows, easier to scan)
- Table headers: lightened from dark charcoal (~#3a–#6a) to medium grey (~#6b–#96) for less visual weight
- TOTAL row: fill changed from light blue to light grey (`#e8e8e8`) with grey top border

---

## [1.1.0] 2026-06-19 — Style refactor and visual polish

### Changed
- Extracted all CSS into a separate `rsu-calculator.css` file; HTML now links it via `<link>`
- TOTAL row: fill changed to light blue (`#cce5ff`), font changed to bold black (`#000`)
- Table section headers (A/B/C/D) now use four distinct shades of grey instead of coloured backgrounds
- Renamed summary card "Cash Returned to You" → "Cash balance returned"

---

## [1.0.0] 2026-06-19 — Initial release

### Added
- `rsu-calculator.html` — single-file browser calculator for Broadcom RSU sell-to-cover vestings
- Multi-tranche table: add/remove grant rows dynamically
- Live recalculation on every input change (no submit button needed)
- Columns: RSU Gross, Vest Price, Gross Value, Sold to Cover, Net Shares, Cost Basis, Sale Price, Sale Value, Fee, Net Proceeds, Gain on S2C, Actual Tax Paid, Effective Rate
- Tax summary cards: gross value, withholding rate, tax should-have-paid, tax actually paid, over/under-withheld, total proceeds, cash returned
- Over-withheld card flips red ↔ green automatically depending on direction of mismatch
- CSV export keyed to the vesting date
- Configurable tax withholding % and currency symbol
- Pre-loaded with Broadcom vesting data from 15 Jun 2026 as a worked example
- `RSU-Excel-Calculator.png` — original Excel model used as reference
- `readme.md` — full feature and usage documentation
