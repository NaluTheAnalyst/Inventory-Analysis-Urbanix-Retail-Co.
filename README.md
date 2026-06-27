# Retail Inventory Analysis — Urbanix Retail Co.

**Portfolio Project | Inventory Health, ABC Analysis & Stock Optimization**
**Tools used:** Microsoft Excel (analysis) → Power BI (visualization)

---

## Business Context

Urbanix Retail Co. is a multi-category retail store (footwear, apparel,
electronics, home & living, and accessories) based in Lagos. Management wants to
understand which products drive revenue, which SKUs are tying up cash as dead
stock, and which items risk running out of stock.

## Project Objective

Analyze 6 months of sales and stock data across 150 SKUs to:

1. Classify products by revenue contribution using ABC analysis
2. Calculate inventory turnover
3. Flag stock status (reorder needed / overstocked / healthy)
4. Identify dead stock tying up capital
5. Produce actionable recommendations for the business

## Project Structure

This project was built in two stages:

**Stage 1 — Analysis (Excel)**
All calculations were built using spreadsheet formulas — no hardcoded values —
so the workbook stays dynamic if source data changes. Core techniques: ABC
analysis via cumulative revenue %, inventory turnover ratio, conditional
stock-status logic (nested IF), and SUMIFS/COUNTIFS-based summary KPIs.

**Stage 2 — Visualization (Power BI)**
The completed analysis was imported into Power BI to build an interactive
dashboard with cross-filtering — letting a viewer click a category or stock
status and see every visual on the page update together, which a static Excel
dashboard can't do.

## Files in This Project

| File | Description |
|---|---|
| `inventory_analysis.xlsx` | Full Excel workbook — Raw Data, Analysis (formulas), Dashboard, Insights write-up |
| `urbanix_raw_data.csv` | Raw inventory dataset only (150 SKUs, 6 months sales history) |
| `urbanix_analysis_for_powerbi.xlsx` | Calculated analysis table, formatted for Power BI import |
| Power BI dashboard | Interactive visualization built from the analysis table (see screenshots / .pbix if included) |

## Key Metrics Calculated

- **Revenue & Gross Profit** per SKU
- **Inventory Turnover Ratio** — units sold ÷ stock on hand
- **Months of Stock Remaining** — stock on hand ÷ average monthly sales
- **ABC Classification** — Class A/B/C based on cumulative revenue share (80/15/5 split)
- **Stock Status** — Dead Stock / Reorder Needed / Overstocked / Healthy
- **Dead Stock Value** — capital tied up in non-moving inventory

## Key Findings

- A small share of SKUs (Class A) drive the majority of revenue — these should
  never run out of stock, since a stockout here has the largest revenue impact.
- A meaningful number of SKUs recorded zero sales across 6 months while still
  holding stock — tying up capital that could be reinvested in fast-moving items.
- Several SKUs are at or below reorder level given current sales velocity,
  risking stockouts.
- A separate group of SKUs is overstocked relative to their sales pace,
  increasing holding costs without a sales benefit.

## Recommendations

1. Prioritize Class A SKUs for safety stock and supplier reliability.
2. Run a clearance or bundling promotion on dead stock to free up tied-up capital.
3. Set up a weekly reorder alert prioritized by ABC class.
4. Reduce reorder quantities for overstocked Class B/C SKUs.
5. Revisit supplier lead times for high-velocity SKUs to reduce required safety stock.

## Methodology Notes

- ABC classification uses cumulative revenue share (A = top ~80% of revenue,
  B = next ~15%, C = remaining ~5%) — the standard Pareto-style convention.
- Inventory turnover ratio uses current stock on hand as a simplified proxy
  in place of average inventory (opening + closing stock ÷ 2), since this
  dataset does not include opening/closing snapshots.
- Stock status logic checks conditions in priority order: Dead Stock (zero
  sales) is checked before Reorder Needed, before Overstocked, before Healthy.


