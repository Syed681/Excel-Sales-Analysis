# AtliQ Hardwares Sales & Financial Analytics (Excel & Power Pivot)

## 📊 Project Overview
This portfolio project provides a comprehensive analysis of AtliQ Hardwares' sales and financial performance across global markets for the fiscal years 2019, 2020, and 2021. The objective is to evaluate historical sales trends, track gross margins, and analyze target variances to support strategic decision-making.

*Note: Raw data files are omitted for confidentiality. The data model, DAX measures, and final reports are documented below.*

## 🗄️ Data Model
The project uses a standard Star Schema optimized in Excel Power Pivot.
* **Fact Tables:** `fact_sales_monthly` (transactional data), `ns_targets_2021` (benchmark data)
* **Dimension Tables:** `dim_customer`, `dim_market`, `dim_product`, `dim_date`

## 🧮 Core Business Logic (DAX)
To maintain a robust and easily explainable model, core calculations utilize fundamental DAX functions:
* **Net Sales:** `SUM(fact_sales_monthly[net_sales_amount])`
* **Time Intelligence (NetSales 21):** `CALCULATE([Net Sales], dim_date[FY]="2021")`
* **Year-Over-Year Growth (21 vs 20):** `DIVIDE([NetSales 21], [NetSales 20], 0)`
* **Target Variance (%):** `DIVIDE([2021 - Target], [target 21], 0)`

## 📈 Key Business Insights
* **Revenue Scaling:** Net sales grew from 87.5M INR in 2019 to 598.9M INR in 2021.
* **Profitability:** Gross Margin percentage contracted slightly from 41.4% in 2019 to 37.3% in 2021.
* **Market Target Variance:** Globally, the market missed the 2021 net sales target by -9.17% (a 54.9M INR deficit).

## 📂 Repository Structure
* `Reports/`: Contains PDF outputs of Customer Performance, Market vs Target, and P&L Statements.
* `Model/`: Contains screenshots of the Star Schema and Measure management window.
