# **Power BI Sales Performance Dashboard**  

📊 **Project Overview**  
An interactive sales analytics dashboard powered by **AdventureWorks Data Warehouse**, tracking team and individual performance across regions, products, and time periods. Features drill-down capabilities, YoY growth analysis, and product/region insights.  

---

### **Video Demo Highlights**  
🎥 **In this walkthrough, you'll see:**  
1️⃣ **Dashboard Tour**:  
   - Interactive filters (Year/Region/Salesperson)  
   - Key metrics: Lifetime Sales, YoY Growth %, Top Products  

2️⃣ **Drill-Down Demo**:  
   - *Rachel Valdez*'s 815% YoY growth analysis  
   - Top-selling products (Bikes: $1.38M) and regional performance  

3️⃣ **Technical Peek**:  
   - Star Schema data model  
   - DAX formulas in action (YoY%, YTD)  

4️⃣ **Live Interactions**:  
   - Slicers for period comparisons  
   - Tooltips and hover effects  

📺 **[Watch the Full Demo Here](https://youtu.be/wv_7u9e8LE0)**  

---

### **Technical Implementation**  
**🔧 Tools**: Power BI, Power Query, DAX  
**📂 Data Model**: AdventureWorks Star Schema  
**📈 Key DAX**:  
```DAX 
YoY % = DIVIDE([Total Sales] - [Total Sales PY], [Total Sales PY])
``` 

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
