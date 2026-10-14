# Retail Sales Performance and Revenue Analysis Dashboard

## Project Description
This project delivers a business intelligence solution designed to track, analyze, and visualize retail sales operations. Built entirely within Microsoft Excel, the dashboard aggregates transactional data across multiple geographic regions, distribution channels, and product categories to provide actionable insights into revenue generation and operational efficiency. The underlying **dataset comprises 2,000 detailed sales records.**

---

## Main Challenge
Stakeholders lacked a centralized mechanism to monitor overall revenue distribution, order volume, and channel-specific performance across a large volume of transactions (2,000 rows). Fragmented reporting methods and manual data compilation hindered swift strategic decision-making, delayed identification of underperforming product categories, and obscured clear visibility into regional sales trends and key business metrics like Average Order Value.

---

### [**Video Demo**](https://youtu.be/WcdfsPAO49A) | [**Dataset**](https://github.com/MuhammadHuzaifaG/Sales-Performance-and-Revenue-Analysis-Excel-Dashboard/tree/main/dataset) | [**Excel Dashboard**](https://github.com/MuhammadHuzaifaG/Sales-Performance-and-Revenue-Analysis-Excel-Dashboard/blob/main/DASHBOARD.PNG)

<img width="879" height="636" alt="11" src="https://github.com/MuhammadHuzaifaG/Sales-Performance-and-Revenue-Analysis-Excel-Dashboard/blob/main/DASHBOARD.PNG" />

## Solution
An interactive Excel-based dynamic reporting dashboard was engineered to streamline data aggregation and visualization. By leveraging structured Excel tables, advanced Pivot Tables, dynamic charts, and synchronized Slicers, the solution automates metric calculations—such as Total Revenue, Total Orders, Total Quantity Sold, and Average Order Value—translating 2,000 raw transaction rows into a clean executive view. This eliminates manual spreadsheet manipulation and provides instant multi-dimensional filtering.

---

## Target Users
* **Sales Managers**: Monitoring overall order volumes, salesperson performance, and regional sales distribution.
* **Regional Operations Directors**: Evaluating channel profitability and geographic demand distribution.
* **Executive Leadership**: Reviewing high-level financial Key Performance Indicators (KPIs), Monthly Revenue Trends, and Top Products by Revenue.

---

## Impact & Key Results
* Consolidated tracking of 2,000 sales transactions into a single-pane-of-glass executive dashboard.
* Automated tracking of key business KPIs: Total Revenue, Total Orders, Total Quantity Sold, and Average Order Value.
* Reduced reporting latency by automating data aggregation through dynamic Pivot Tables.
* Delivered clear visibility into sales channel contributions (Online, Retail Store, Marketplace, etc.).
* Enabled granular tracking of top products and category performance to optimize inventory and marketing strategies.

---

## Tech Stack
* **Primary Tool**: Microsoft Excel (Office 365 / Excel 2016+)
* **Core Features**: Structured Tables (`ListObject`), Pivot Tables, Slicers, Calculated Fields, and Data Validation Rules.

<img width="879" height="636" alt="11" src="https://github.com/MuhammadHuzaifaG/Sales-Performance-and-Revenue-Analysis-Excel-Dashboard/blob/main/screenshots/DATASET_OVERVIEW.PNG" />

---

## Dataset Schema & Sample Data

The dataset consists of **2,000 rows** of transactional records. Below is the schema definition, including column descriptions based on data auditing checks, followed by the first 5 rows reflecting the data structure.

### Column Definitions & Data Types
* `Order ID`: Text (Unique order reference used for order count calculations)
* `Date`: Date (Order date required for timeline/month grouping)
* `Region`: Text (Sales region operating zone)
* `Sales Channel`: Text (Distribution method: Online, Retail Store, Marketplace, etc.)
* `Customer Type`: Text (Customer classification: New or Returning)
* `Product Category`: Text (Product grouping macro classification)
* `Product`: Text (Specific product name)
* `Salesperson`: Text (Employee handling the transaction)
* `Quantity`: Integer / Numeric (Number of units sold, used for sum calculations)
* `Unit Price`: Numeric / Currency (Price per unit)
* `Discount`: Percentage (Discount given on transaction)
* `Revenue`: Numeric / Currency (Final sales amount, used for sum calculations)

### Sample Data (First 5 Rows)
| Order ID | Date | Region | Sales Channel | Customer Type | Product Category | Product | Salesperson | Quantity | Unit Price | Discount | Revenue |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ORD-1001 | 4/9/2026 | West | Online | New | Accessories | Mouse Pad | Sofia Tan | 4 | 13.1 | 0% | 52.38 |
| ORD-1002 | 6/9/2026 | East | Retail Store | Returning | Storage | Memory Card 256GB | Nora Chen | 3 | 81 | 3% | 235.71 |
| ORD-1003 | 6/10/2026 | West | Online | New | Networking | Ethernet Cable | Ben Ho | 2 | 17.46 | 0% | 34.92 |
| ORD-1004 | 8/26/2026 | North | Retail Store | New | Networking | Wi-Fi Router | Aisha Lim | 6 | 252 | 5% | 1436.4 |
| ORD-1005 | 8/23/2026 | North | Corporate Sales | Returning | Networking | Mesh Wi-Fi Set | Aisha Lim | 7 | 654.75 | 5% | 4354.09 |

---

## Business Requirements & Dashboard Mapping

The table below outlines how executive business requirements map directly to specific dashboard visuals and underlying dataset columns:

| Dashboard Requirement | Dashboard Element | Column Used | Description / Purpose |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | KPI Card: Total Revenue | `Revenue` | Evaluates gross business revenue. |
| **Total Orders** | KPI Card: Total Orders | `Order ID` | Counts total order volume across transactions. |
| **Quantity Sold** | KPI Card: Total Quantity Sold | `Quantity` | Tracks aggregate unit sales volume. |
| **Average Order Value** | KPI Card: Average Order Value | `Revenue` | Calculates mean revenue per transaction. |
| **Monthly Revenue Trend** | Line Chart: Revenue by Month | `Date` and `Revenue` | Tracks sales momentum over time. |
| **Regional Performance** | Column/Bar Chart: Revenue by Region | `Region` and `Revenue` | Compares geographic sales distribution. |
| **Product Category Performance** | Bar Chart: Revenue by Product Category | `Product Category` and `Revenue` | Assesses revenue contribution by product group. |
| **Sales Channel Contribution** | Doughnut Chart: Revenue by Sales Channel | `Sales Channel` and `Revenue` | Analyzes performance across Online, Retail, etc. |
| **Top Products by Revenue** | Bar Chart: Top 5 Products by Revenue | `Product` and `Revenue` | Highlights highest grossing specific product items. |

---

## Methodology & Data Auditing

### 1. Data Quality Checks & Preparation
Prior to building calculations, strict data auditing checks were applied to guarantee data integrity:
* **Header Verification**: Ensured no blank column headers existed, allowing proper PivotTable field mapping.
* **Row Integrity**: Confirmed there were no fully blank rows inside the 2,000 data rows to prevent broken data ranges.
* **Date Parsing**: Validated that all entries in the `Date` column were formatted as true dates required for timeline and monthly grouping.
* **Numeric Validation**: Ensured `Revenue`, `Quantity`, and `Unit Price` were formatted strictly as numbers for mathematical sum and average functions.
* **Category Consistency**: Standardized spelling across `Region` and `Product Category` to prevent duplicate field creation.
* **Order ID Availability**: Verified complete presence of `Order ID` entries to maintain accurate order counts.

### 2. Pivot Table Architecture
* Created distinct, purpose-built Pivot Tables connected to the main data table to compute high-level KPI cards (Total Revenue, Total Orders, Total Quantity, AOV) as well as chart metrics (Monthly Trends, Category Breakdown, Top 5 Products).
* Structured dynamic field summaries ensuring clean aggregations without manual formula updates.

### 3. Dynamic Filters and Slicers
* Implemented interactive Slicers for `Region`, `Sales Channel`, and `Customer Type`.
* Configured Report Connections so that selecting any slicer filter automatically updates all Pivot Tables, KPI cards, and associated visual charts across the dashboard in real time.

### 4. Dashboard Visual Layout
* Placed primary KPI cards prominently across the top of the reporting view.
* Positioned high-level trend visuals (Monthly Revenue Trend, Revenue by Region) alongside categorical and product distribution charts (Top 5 Products by Revenue, Revenue by Sales Channel).
* Applied a clean, uncluttered layout with coherent formatting and grid alignment suitable for executive reporting.

---

## Prerequisites and Local Setup Instructions

### Prerequisites
* Microsoft Excel (Office 365, Excel 2016, 2019, 2021, or Excel for Mac) with full support for Pivot Tables, Pivot Charts, Slicers, and structured table references.

### Local Setup Instructions
1. Download the project files to your local machine.
2. Navigate to the project directory and locate the primary workbook file (e.g., `Sales_Data.xlsx`).
3. Open the file in Microsoft Excel.
4. Click **Enable Editing** if prompted by the Excel security bar.
5. Navigate to the `Dashboard` tab and utilize the interactive Slicers to filter sales metrics dynamically by region, sales channel, or customer type.
