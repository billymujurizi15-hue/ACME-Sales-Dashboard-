ACME Sales Dashboard — Power BI Project

An interactive Power BI dashboard analyzing North American sales performance for ACME Corp, covering 2017–2018 order-level transactions across Canada and the United States.

Overview

This project transforms raw sales order data into a single-page executive dashboard, surfacing revenue trends, product performance, geographic distribution, and sales rep contribution at a glance.

MetricValueTotal Revenue$2,078,342Orders Analyzed369Date RangeJan 2017 – Dec 2018CountriesCanada, United StatesProduct CategoriesFLUX, KENO, DAROProducts11Sales Reps10

Repository Contents

FileDescriptionproject_one.pbixPower BI Desktop file — full data model, DAX measures, and reportACME_Sales_Report.xlsxSource dataset (order-level sales records)README.mdProject documentation (this file)

Data Structure

The source data (ACME_Sales_Report.xlsx) contains one table, ACME Sales North America, with the following fields:

OrderId, SalesDate, ClientID, Company, Country, State, City, Street, SalesRegion, SalesRepID, SalesRep, ProductName, Category, Released, Revenue

Dashboard Contents

The report page includes:


KPI cards — Total Revenue, Distinct Clients, Distinct Products, Revenue per Client, Revenue per Product
Country slicer — filter the whole page by Canada / United States
Clustered column chart — Revenue by Month
Funnel chart — Revenue by Product
Stacked area chart — Revenue by State/Province over time


 Key DAX Measures

daxTotal Revenue = SUM('ACME Sales North America'[Revenue])

Distinct Clients = DISTINCTCOUNT('ACME Sales North America'[ClientID])

Distinct Products = DISTINCTCOUNT('ACME Sales North America'[ProductName])

Revenue per Client = DIVIDE([Total Revenue], [Distinct Clients])

Revenue per Product = DIVIDE([Total Revenue], [Distinct Products])

Tech Stack


Power BI Desktop — data modeling, DAX, and report design
Excel — source data storage


 How to Use


Clone this repository:


bash   git clone https://github.com/<your-username>/acme-sales-dashboard.git


Open project_one.pbix in Power BI Desktop (free).
Use the Country slicer to explore Canada vs. United States performance.
Click the Refresh button in Power BI if you replace ACME_Sales_Report.xlsx with updated data — the data model is already connected to that source table.


Key Insights


Revenue is concentrated across three product categories (FLUX, KENO, DARO), giving a clear lens for category-level performance comparison.
The funnel chart highlights which individual products drive the largest share of revenue.
The state/province area chart reveals how revenue shifts geographically over the two-year window, useful for identifying growth or declining markets.


Notes


This is a portfolio/learning project built to practice Power BI data modeling, DAX, and dashboard design principles.
Data is illustrative/sample sales data, not real ACME Corp financials.


📄 License

This project is shared for educational and portfolio purposes. Feel free to fork and adapt it for your own learning.


Author: Mujurizi Billy
