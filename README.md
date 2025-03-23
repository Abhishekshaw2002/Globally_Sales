# Globally_Sales

# Problem Statement:
Global sales data is fragmented across regions and systems, leading to inefficiencies in tracking performance. Key challenges include:
Lack of consolidated visibility into monthly/weekly sales targets and achievements.
Difficulty identifying top-performing customers, products, and regions.
Manual reporting delays and inconsistent currency/region formatting.
Inability to monitor real-time progress toward targets.

#  Objective:
Develop a Power BI dashboard to:
Track KPIs: Monthly/Weekly Sales vs. Targets, Top 3 Customers, Top 10 Products, Sales by Region/Country.
Provide real-time insights for agile decision-making.
Automate data integration and refresh for global teams.

#  Technology Used:
Power BI: Dashboard design and visualization.
Power Query: Data transformation (currency conversion, time zones).
DAX: Advanced calculations for targets and rankings.
SQL Server/Cloud Storage (AWS S3): Centralized data repository.
Power BI Gateway: Scheduled data refresh.
Excel: Initial data validation.

#  Scope of the Project:
Consolidate sales data from 50+ countries.
Visualize KPIs with interactive filters (e.g., region, product category).
Compare actual sales against weekly/monthly targets.

# Concept Of the project:
Data Sources: SQL (transaction data), Excel (targets), APIs (currency rates).
ETL: Clean, standardize, and merge data (e.g., convert USD to local currencies).
Data Model: Star schema with fact tables (Sales, Targets) and dimensions (Time, Product, Customer).
Visualization: Maps, barcharts, and tables for KPIs.
Deployment: Publish to Power BI Service with row-level security.

#  Requirement Gathering:
KPIs:
Monthly/Weekly Sales vs. Targets | Top 3 Customers | Top 10 Products | Sales by Region/Country.
Data Needs: Historical sales, target sheets, customer metadata, currency rates.
User Preferences: Drill-down filters, export to PDF/Excel, mobile compatibility.

#  Model Development:
Tables:
Fact: Sales (OrderID, Revenue, Quantity), Targets (Month/Week, Target Value).
Dimension: Time (Month, Week), Customer, Product, Region, Country.
Relationships: Link Sales to Time, Product, and Customer; Targets to Time.
Data Cleaning: Standardized country names, aligned time zones, resolved currency mismatches.

# DAX Queries & Results:
1) Total Sales = SUM(Sales[Revenue]) 
   {This query shows total sales}
2) Top Customers = TOPN(3, SUMMARIZE(Sales, Customer[Name], "Total", SUM(Sales[Revenue])), [Total], DESC)  
   {This query shows top 3 customers}
3) Weekly Achievement = DIVIDE([Total Sales], SUM(Targets[Weekly Target]), 0)
   {This query shows Weekly Target Achievement}
4) Top Products = TOPN(10, VALUES(Product[Name]), [Total Sales], DESC)
   {This query shows Top 10 Products}

# Data Refresh:
Automated Refresh: Daily refresh via Power BI Gateway for SQL/cloud data.
Manual Override: Refresh ad-hoc for urgent updates (e.g., new targets).

#  Challenges Faced:
Time Zone Alignment: Harmonized timestamps using Power Query.
Currency Conversion: Dynamically applied exchange rates using DAX.
Data Volume: Optimized queries with aggregations for faster loading.
Target Variance Calculation: Resolved mismatches between weekly/monthly granularity.

#  Future Improvement Scope:
Integrate real-time CRM data (e.g., Salesforce).
Add predictive analytics for target forecasting.
Enable multi-language support for global users.
Implement anomaly detection for sudden sales drops.

#  Conclusions:
The Power BI dashboard provides a unified view of global sales performance, enabling teams to track targets, identify top customers/products, and make data-driven decisions. Automated refreshes and role-based access ensure scalability and security.

