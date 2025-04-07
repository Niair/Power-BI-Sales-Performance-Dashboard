**Power BI Sales Performance Dashboard**  

📊 **Project Overview**  
An interactive sales analytics dashboard powered by **AdventureWorks Data Warehouse**, designed to track individual and team performance across regions, products, and time periods. Features drill-down capabilities, YoY growth analysis, and product/region performance insights to drive data-driven sales strategies.  

---

### **Data Warehouse & Star Schema Implementation**  
**1. Data Source: AdventureWorks OLAP Database**  
- **Fact Tables (Transactional Data)**:  
  - `FactInternetSales` (Online orders)  
  - `FactResellerSales` (B2B transactions)  
  - `FactSalesQuota` (Sales targets)  
- **Dimension Tables (Descriptive Data)**:  
  - `DimEmployee` (Sales team: Names, Regions)  
  - `DimProduct` (Categories: Bikes, Clothing)  
  - `DimDate` (Time hierarchy: Fiscal Year/Month)  
  - `DimSalesTerritory` (Geography: Country/Group)  

**2. Star Schema Model**  
- **Central Fact Table**: `FactInternetSales` (linked to dimensions via keys like `ProductKey`, `TerritoryKey`).  
- **Optimized for Analytics**: Enables fast aggregations (e.g., SUM of sales by region).  

**3. ETL Process (Power Query)**  
- **Cleaned Data**: Standardized currencies (₹ → $), handled nulls in `Total Sales PY`.  
- **Calculated Columns**: Added `YoY%` and `YTD Sales` during transformation.  

---

📸 **Dashboard Screenshots** *(Add visuals here)*  
- **Team Performance**: Table with filters for Region/Year.  
- **Drill-Down View**: Rachel Valdez’s 815% YoY growth in Germany.  
- **Product Breakdown**: Bikes dominate sales ($1.38M).  

---

🛠️ **Technical Implementation**  
**Metrics (DAX)**  
```DAX
YoY % = DIVIDE([Total Sales] - [Total Sales PY], [Total Sales PY])  
Sales YTD = TOTALYTD(SUM(FactInternetSales[SalesAmount]), DimDate[Date])  
```  
**Tools**: Power BI (Visuals), Power Query (ETL), DAX (Metrics).  

▶️ **How It Works**  
1. **Extracts** data from AdventureWorks DW.  
2. **Models** it in a star schema for efficient queries.  
3. **Visualizes** KPIs with interactive filters (Year/Region).  
