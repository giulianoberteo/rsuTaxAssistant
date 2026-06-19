# Changelog

All notable changes to the RSU Tax Calculator are recorded here.

Format: `[version] YYYY-MM-DD — summary`

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
