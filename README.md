# Globally_Sales

# Problem Statement:
The global sales team struggles with fragmented data across multiple Excel files, leading to inefficiencies in tracking performance. Key challenges include:
Manual consolidation of sales data from 50+ countries, resulting in errors and delays.
Difficulty tracking monthly/weekly sales targets and identifying top customers/products.
Lack of dynamic dashboards to visualize KPIs like regional performance or target achievement.
Inconsistent formatting and currency conversions across regions.

#  Objective:
Develop an Excel-based solution to:
Automate consolidation and analysis of global sales data.
Track KPIs: Monthly/Weekly Sales vs. Targets, Top 3 Customers, Top 10 Products, Sales by Region/Country.
Create interactive dashboards for real-time decision-making.

#  Technology Used:
Microsoft Excel: Core platform for data modeling, formulas, and dashboards.
Power Query (Excel): Data extraction, transformation, and loading (ETL).
Power Pivot: Advanced data modeling (optional for large datasets).
VBA Macros: Automation of repetitive tasks (e.g., data refresh).
PivotTables/PivotCharts: Dynamic reporting.

#  Scope of the Project:
Integrate sales data from multiple Excel/CSV files.
Calculate KPIs using formulas and PivotTables.
Build dashboards with slicers for interactive filtering.

# Concept Of the project:
Data Sources: Country-specific Excel files, CSV exports from ERP systems.
ETL: Use Power Query to clean, merge, and standardize data (e.g., currency conversion).

# Data Model:
Tables: Sales (TransactionID, Date, Product, Customer, Revenue), Targets (Month/Week, Target Value).
Formulas: SUMIFS, INDEX-MATCH, RANK.EQ for KPI calculations.
Visualization: Dashboards with charts (e.g., bar graphs, maps via Power View) and slicers.

#  Requirement Gathering:
KPIs:
Monthly/Weekly Sales vs. Targets | Top 3 Customers | Top 10 Products | Sales by Region/Country.
Data Sources: Excel files (sales transactions, targets), CSV (customer metadata).
User Preferences: Interactive filters (slicers), printable summary sheets, auto-refresh.

#  Model Development:
Raw Data Sheet: Consolidated sales data cleaned via Power Query.
KPIs Sheet:
Total Sales: =SUMIFS(Sales[Revenue], Sales[Month], "Jan-2024")
Top 3 Customers:
=INDEX(Customer[Name], MATCH(LARGE(SUMIFS(Sales[Revenue], Sales[Customer], Customer[Name]), 1),
SUMIFS(Sales[Revenue], Sales[Customer], Customer[Name]), 0))

Monthly Target Achievement: =Total_Sales / VLOOKUP(Month, Targets, 2, FALSE)

# Dashboard Sheet:
PivotTables for Sales by Region and Top 10 Products.
Slicers for Country and Product Category.
Conditional formatting for target variance.

#  Challenges Faced:
Manual Errors: Resolved with Power Query for automated data cleaning.
Large Datasets: Optimized using Excel Tables and Power Pivot.
Dynamic Top N Lists: Used array formulas and RANK.EQ for flexibility.
Currency Conversion: Created a lookup table with exchange rates.

#  Future Improvement Scope:
Migrate to Power BI for real-time dashboards and better scalability.
Integrate with SQL databases to replace CSV/Excel data sources.
Develop VBA macros for auto-emailing reports.
Use Power Query to pull live currency rates from APIs..

#  Conclusions:
The Excel solution streamlines global sales tracking, automating data consolidation and KPI calculations. Interactive dashboards enable teams to monitor targets, top customers/products, and regional performance efficiently. While Excel has limitations with scalability, it provides a cost-effective and user-friendly solution for immediate needs.

# Screenshot:
Include screenshots of Excel dashboard, data model and visualizations 

