
# Power BI Exam Project – Sales, Product & Customer Insights

##  Project Overview
This project demonstrates my approach to solving various analytical and visualization tasks in Power BI, covering:
- Data preparation & modeling
- Creating calculated columns & DAX measures
- Designing interactive report pages
- Implementing bookmarks, page navigation, and filters
- Publishing to Power BI Service & building a live dashboard

The analysis focuses on **Sales**, **Product Performance**, and **Customer Insights**, with additional advanced visuals such as decomposition trees, custom bullet charts, and KPI gauges.

![Alt text](Screenshots\visual_gallery.png)



## Section 1: Data Import and Transformation
- Imported multiple datasets including **Sales**, **Customers**, **Products**, **Dates**, 
- Created a **Geography** table by extracting City, State-Province, Country-Region from Customers - **Regions**.
- Performed transformations in **Power Query**:
  - Cleaned column names, removed duplicates, and ensured proper data types.
  - Handled missing values (e.g., removed invalid postal codes in Customers table).
  - Created calculated columns (e.g., `Budget = 1.2 * Cost`).
  - Created the custom column **Profit** = "Profit" = SalesAmount - (Quantity 
* Cost from Products table) as well as a conditional column for Sales Amount Level
  - Added a date hierarchy from the Date table for time intelligence functions.
![Alt text](Screenshots\Customer_power_query_steps.png)
![Alt text](Screenshots\Product_power_query_steps.png)
![Alt text](Screenshots\Sales_power_query_steps.png)
![Alt text](Screenshots\Date_power_query_steps.png)
![Alt text](Screenshots\shot1.png)
![Alt text](Screenshots\shot2.png)
![Alt text](Screenshots\shot3.png)
![Alt text](Screenshots\shot4.png)
**Challenge Faced:**  
I encountered issues fixing invalid postal codes in the Customers table. The data was inconsistent and did not align with mapping visuals, so I dropped the column to maintain model integrity.
![Alt text](Screenshots\Customer_powerquery_postal_code.png)

---

## Section 2: Data Modeling

![Alt text](Screenshots\Data_Model.png)
- Established relationships:
  - **One-to-Many** between Date and Sales (DateKey).
  - Linked Customers → Sales, Products → Sales, Regions → Customers.
- Created a **Star Schema** for optimized performance.
- Ensured all fields had proper cardinality and cross-filter direction for correct aggregation.
- Added calculated columns and measures for KPIs.

---

## Section 3: Creating Visualizations
## Sales Overview Page**
![Alt text](Screenshots\sales_report.png)


#### 1. Profit Performance
- **Total Profit:** $10.67M  
- **Total Sales Amount:** $97.88M  
- **Sales Target:** $107.67M  
- **Variance:** –$9.79M (missed target)  

---

#### 2. Sales Concentration by Product Category
- **Bikes**: ~$83.36M (85.17% of total sales)  
- **Components, Clothing, Accessories**: ~14.83% combined  
- Heavy reliance on bike sales for revenue generation.

---

#### 3. Sales Amount by Sales Category
- **Low** category: 85.15% of sales amount  
- **Medium** and **High** categories contribute minimally.  
- Suggests limited large-ticket sales.

---

#### 4. Sales Trend (Year & Month)
- **Upward growth trend** from 2018 to 2020.  
- Clear **seasonal peaks** and dips visible in monthly sales.

---

#### 5. Geographic Sales Distribution
- **North America:** Burien, Bellflower, Burbank (USA)  
- **Europe:** London (UK), Paris (France), Frankfurt & Metz (Germany)  
- **Australia:** Townsville, Wollongong  
- Diverse international market presence.

## Product Analysis Page**
![Alt text](Screenshots\product_report.png)


#### 1. Outlier Overview
- **Max Outlier Value:** $27,893.62  
- **Total Outlier Sales:** $12.29M  
- **Outlier Count:** 1,136 transactions  
- Significant revenue contribution from extreme high-value sales.

---

#### 2. Product Performance
- **Top Selling Product by Sales & Profit:** Mountain-200 Black, Size 38 — $4.4M profit.  
- Other strong performers include:
  - Mountain-200 Black, Size 42 — $4.0M profit  
  - Mountain-200 Silver, Size 38 — $3.7M profit  

---

#### 3. Category Performance Against Budget
- **Bikes** category dominates sales, far exceeding other categories.  
- Accessories, Clothing, and Components have negligible sales compared to Bikes.

---

#### 4. Sales Category and Quantity Relationship
- High sales quantity does not always correlate with high profit.  
- **Low** sales category recorded large quantities but relatively low profit margins.  
- **High** sales category products deliver higher profits with smaller quantities.

---

#### 5. Quantity & Profit Summary
- **Total Quantity Sold:** 427.17 units (across all products & years).  
- Performance is highly skewed toward a few high-profit, low-quantity products.


## Customer Insights Page**
![Alt text](Screenshots\customer_report.png)


#### 1. City-Level Customer Concentration
- **London**: 1,555 customers (largest customer base).
- **Paris**: 1,163 customers (second largest).
- Combined, London and Paris account for a significant share of all customers.

---

#### 2. Geographic Sales Concentration
- Top 5 cities — **London, Paris, Burien, Bellingham, Concord** — hold the majority of customers.
- Indicates sales opportunities are concentrated in a few geographic hubs.

---

#### 3. High-Value Customers
- Certain customers such as **AW00012650** and **AW00011242** each generate **$4.2M+ in profit**.
- A small number of high-value clients contribute disproportionately to total profits.

---

#### 4. Overall Sales & Profit
- **Total Sales (2018–2021):** $72.49M  
- **Total Profit:** $183.55M  
- Suggests strong margins and/or premium pricing.

---

#### 5. Repeat Purchase Behavior
- **Customer Count:** 18.48K  
- **Total Orders:** 116K  
- **Average Orders per Customer:** ~6.3  
- Indicates strong customer retention and repeat buying patterns.

---

## Section 4: Building Reports and Dashboards
![Alt text](Screenshots\product_report_showing_bookmarks.png)
- Published report to Power BI Service.
- Created a new dashboard and pinned key visuals from all report pages.
- Added Q&A tile with natural language query (“Top selling product in 2024”).
- Applied consistent dashboard theme and added company logo via image URL.
- Enabled **mobile layout optimization** for accessibility.
- Used bookmarks for navigation between pages.
- Included a text note documenting outliers (SalesAmount > 99th percentile).



## Section 4: Advanced Features and DAX
### Row-Level Security

![Alt text](Screenshots\European_Manager_Role.png)
![Alt text](Screenshots\European_Manager.png)
![Alt text](Screenshots\US_manager_role_creation.png)



###Files in Repository
- `Endsem_BI.pbix` → Power BI project file.
- `README.md` → This documentation.
- `screenshots/` → PNG images of report pages and visuals.
- `DSA3050_END_SEM.pdf` → pdf of reports



