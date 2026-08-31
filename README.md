# Vendor Performance Dashboard

** Data Visualization ** — a Power BI dashboard analyzing vendor and brand sales performance, built to surface which vendors and brands drive revenue, which are underperforming, and where inventory is moving slowly.

## Objective

Turn raw purchase and sales data into a single-page interactive dashboard that tells a clear story: who the top-performing vendors and brands are, how healthy inventory turnover looks across vendors, and where profit margin and sales volume suggest underperformance.

## Tools Used

- **Power BI Desktop** — data modeling, DAX measures, visuals
- **Power Query** — data cleaning and shaping

## Data Model

The report is built on four related tables:

| Table | Purpose |
|---|---|
| `final_table` | Core fact table — purchase price, sales price/quantity/dollars, freight cost, gross profit, profit margin, stock turnover, excise tax, unsold units, brand and vendor names |
| `BrandPerformace` | Brand-level rollup — average profit margin, target brand flag, total sales |
| `purchase contribution` | Vendor-level purchase contribution % and total purchase dollars |
| `LowTurnOverVendor` | Vendors flagged for low average stock turnover |

See `screenshots/data_model.png` for the full relationship diagram.

## Key Metrics (KPI cards)

| Metric | Value |
|---|---|
| Total Purchase ($) | 307.34M |
| Total Sales ($) | 441.41M |
| Total Gross Profit | 134.07M |
| Profit Margin (%) | 331.62K |
| Unsold (units) | 2.71M |

## Dashboard Visuals & Insights

- **Purchase Contribution (%)** — donut chart showing each vendor's share of total purchase spend (Diageo North America, Martignetti, Pernod Ricard USA, Jim Beam Brands, Bacardi USA, and others).
- **Top Vendor by Sales** — bar chart ranking vendors by total sales dollars; Diageo North America leads, followed by Martignetti and Pernod Ricard.
- **Top Brands by Sales** — bar chart of best-selling brands; Jack Daniels, Tito's Handmade Vodka, and Grey Goose Vodka top the list.
- **Sum of AvgStockTurnOver by Vendor** — highlights vendors with the lowest average stock turnover (Dunn Wine Brokers, Circa Wines, Park Street Imports, Highland Wine Merchants, Alisa Carr Beverages) — a signal for slow-moving inventory.
- **Low Performing Brands** — scatter plot of profit margin vs. total sales, used to spot brands that sell in volume but return low margin (or vice versa).

The full exported report is in `report/vendor_performance_sales_dashboard.pdf`.

## Repository Structure

```
vendor-performance-dashboard/
├── README.md
├── data/                  # raw and/or cleaned source data
├── powerbi/               # .pbix Power BI file
├── screenshots/           # data model + dashboard screenshots
│   └── data_model.png
└── report/                # exported dashboard report
    └── vendor_performance_sales_dashboard.pdf
```

## How to View

1. Open `powerbi/vendor_performance_dashboard.pbix` in Power BI Desktop to explore the interactive report.
2. Or view `report/vendor_performance_sales_dashboard.pdf` for a static snapshot of all visuals.
