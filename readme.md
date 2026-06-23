# RSU Tax Calculator

A single-file, browser-based calculator for analysing Broadcom RSU vestings processed through **Charles Schwab Equity Awards** (sell-to-cover method).

No server, no install, no dependencies — open `rsu-calculator.html` in any modern browser and it works offline.

---

## What it does

Given the details of a sell-to-cover vesting event, the calculator:

- Computes **gross vesting value** for each tranche (RSU count × vest price)
- Derives **net shares** kept after the sell-to-cover
- Calculates **cost basis**, **sale value**, **net proceeds** (after broker fee), and **gain on the sell-to-cover** per tranche
- Compares what Schwab **actually withheld** against what you **should have paid** at your withholding rate
- Surfaces the **over/under-withheld amount** and the **cash Schwab returns** to you after tax settlement

---

## Features

| Feature | Detail |
|---|---|
| Multi-tranche support | Add or remove grant rows dynamically |
| Live recalculation | Every cell updates instantly on any input change |
| Persistent state | All inputs auto-saved to `localStorage`; restored on page reload |
| Configurable tax rate | Set your RSU withholding % (e.g. 55.25%) |
| Currency symbol | Switchable ($ default; change to £, €, etc.) |
| Over/under detection | Summary card flips red ↔ green depending on direction |
| S2C Capital Gain/Loss | Summary card shows gain or loss vs vest price, for self-assessment |
| CSV export | Downloads a full breakdown for the vesting date |
| Pre-loaded example | Ships with the 15 Jun 2026 Broadcom vesting as a worked example |
| Zero dependencies | Pure HTML + CSS + vanilla JS, single file |

---

## How to use

1. Open `rsu-calculator.html` in a browser (double-click or `open rsu-calculator.html`)
2. Set the **Vesting Date** and **RSU Tax Withholding %** at the top
3. Each row represents one grant tranche — edit the yellow (input) cells:
   - RSU Gross count, Vest Price, Sold-to-Cover shares, Sale Price, Broker Fee
   - **Actual Tax Paid** — copy from your Schwab confirmation
4. Blue cells are calculated automatically
5. Read the **Tax Summary** cards at the bottom
6. Click **Export CSV** to save a record

---

## Columns explained

| Column | Type | Formula |
|---|---|---|
| Gross Value | Calc | RSU Gross × Vest Price |
| Net Shares | Calc | RSU Gross − Sold to Cover |
| Cost Basis | Calc | Sold to Cover × Vest Price |
| Sale Value | Calc | Sold to Cover × Sale Price |
| Net Proceeds | Calc | Sale Value − Fee |
| Gain on S2C | Calc | Net Proceeds − Cost Basis |
| Effective Rate | Calc | Actual Tax Paid ÷ Gross Value |

### Summary cards

| Card | Colour | Formula |
|---|---|---|
| Total Gross Vesting Value | Blue | Σ (RSU Gross × Vest Price) |
| RSU Tax Withholding % | Blue | Input value |
| Total Net Proceeds | Green | Σ (Sale Value − Fee) |
| S2C Capital Gain / Loss | Green/Red | Σ (Net Proceeds − Cost Basis) |
| Tax I Should Have Paid | Yellow | Total Gross Value × Withholding % |
| Tax I Actually Paid | Yellow | Σ Actual Tax Paid (from Schwab) |
| Total Proceeds from S2C | Orange | Σ Net Proceeds (money that went to tax) |
| Schwab Over-Withheld | Red/Green | Actually Paid − Should Have Paid |
| Cash Balance Returned | Green | Total Net Proceeds − Tax I Actually Paid |

---
