Here's your enhanced YouTube video description with a dedicated **Video Content** section that clearly outlines what you'll be showing in the demo:

---

# **Power BI Sales Performance Dashboard**  

📊 **Project Overview**  
An interactive sales analytics dashboard powered by **AdventureWorks Data Warehouse**, designed to track individual and team performance across regions, products, and time periods. Features drill-down capabilities, YoY growth analysis, and product/region performance insights to drive data-driven sales strategies.  

---

### **What You'll See in the Video Demo**  
🎥 **In this walkthrough, I'll show you:**  
1️⃣ **Dashboard Overview**:  
   - How the main dashboard filters work (Year, Region, Salesperson).  
   - Key metrics like Lifetime Sales, YoY Growth %, and Top Products.  

2️⃣ **Drill-Down Demonstration**:  
   - Clicking into *Rachel Valdez*’s profile to explore her 815% YoY growth.  
   - Analyzing her top-selling products (Bikes: $1.38M) and regional performance (Germany).  

3️⃣ **Technical Backend**:  
   - A quick peek at the **Star Schema** data model in Power BI.  
   - How DAX formulas (like `YoY%`) calculate critical metrics.  

4️⃣ **Interactive Features**:  
   - Using slicers to compare 2023 vs. 2022 sales.  
   - Hover effects and tooltips for deeper insights.  

🔗 **GitHub Repository**: [Insert Your Link Here] *(For PBIX file, DAX scripts, or documentation)*  

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

🛠️ **Technical Implementation**  
**Metrics (DAX)**  
```DAX
YoY % = DIVIDE([Total Sales] - [Total Sales PY], [Total Sales PY])  
Sales YTD = TOTALYTD(SUM(FactInternetSales[SalesAmount]), DimDate[Date])  
```  
**Tools**: Power BI (Visuals), Power Query (ETL), DAX (Metrics).  

---

📸 **Dashboard Screenshots** *(Add visuals here)*  
- **Team Performance**: Table with filters for Region/Year.  
- **Drill-Down View**: Rachel Valdez’s 815% YoY growth in Germany.  
- **Product Breakdown**: Bikes dominate sales ($1.38M).  

[Watch the Full Demo Here]([https://youtu.be/wv_7u9e8LE0](https://youtu.be/wv_7u9e8LE0))  
