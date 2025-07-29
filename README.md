# Blinkit Grocery Sales Analysis Dashboard

---

## 1. Business Requirements and KPIs

The starting point of this project was understanding Blinkit’s need for **a single interactive dashboard** that could summarize sales performance across products, outlets, and geographies. Blinkit wanted to identify **which products and categories were driving revenue**, how **fat content preferences** varied by location and store type, and which **outlet tiers** contributed most to overall sales.  

Equally important was the ability to **track key performance indicators (KPIs)** that would provide instant insights into the company’s overall performance. The four KPIs identified were:

- **Total Sales ($1.2M)** – The total revenue across all products and outlets.  
- **Average Sales per Item ($141)** – A measure of typical basket size or customer spend.  
- **Total Number of Items Sold (8,523)** – Indicates sales volume.  
- **Average Rating (3.9)** – Provides a customer satisfaction perspective.

These KPIs formed the foundation of the dashboard’s design and were referenced throughout other visualizations to maintain consistency and relevance.

<img width="1221" height="425" alt="Screenshot 2025-07-12 201516" src="https://github.com/user-attachments/assets/310ed73e-9d8f-4592-8e42-4ce2c520a2a6" />


Understanding the KPIs also influenced how the **visualizations were chosen**. Each metric needed supporting charts to contextualize performance — for example, a **donut chart for fat content distribution** to understand customer health preferences, **bar charts for product category performance**, and **line charts for outlet establishment year trends**.

<img width="1740" height="800" alt="Screenshot 2025-07-12 201535" src="https://github.com/user-attachments/assets/fa1633ac-d566-4cbb-b6d0-a164f0d2b5f7" />


Another critical element during this phase was ensuring the dashboard served **multiple stakeholders**: category managers needed product-specific insights, marketing teams required customer preference trends, and sales teams demanded location- and outlet-wise performance. Thus, while KPIs gave a quick snapshot, supporting charts allowed **drill-down analysis**.

<img width="1779" height="677" alt="Screenshot 2025-07-12 201608" src="https://github.com/user-attachments/assets/4e9a5dfc-63bf-436f-8052-90466d628629" />


---

## 2. Raw Dataset

The dataset comprised **8,500+ transaction records** collected from Blinkit’s grocery operations. Each record captured multiple dimensions such as **Item Type, Fat Content, Outlet Size, Outlet Type, Establishment Year, Sales, Ratings, and Location Tier**.  

However, the raw dataset was far from analysis-ready. It contained **inconsistent fat content labels** like `LF`, `low fat`, and `Low Fat`; outlet names were **non-standardized**; and critical columns like `Item Weight` contained **missing values**. Additionally, visibility fields included **zero values**, which were either erroneous or irrelevant for analysis.

<img width="1586" height="795" alt="Screenshot 2025-07-13 231006" src="https://github.com/user-attachments/assets/26dd9e02-f628-487a-b9b7-d7016c2c5de4" />


Analyzing the dataset in its raw form would have led to misleading conclusions. Therefore, a **structured cleaning and transformation process** was planned using Power Query to ensure accuracy and repeatability for future data updates.

---

## 3. Power Query ETL Process

Power Query was used as the backbone for the **Extract, Transform, Load (ETL)** process. This ensured that data cleaning steps were automated and could be refreshed with new incoming data.

### **Key steps in the ETL process included:**
- **Standardizing Fat Content:** Replaced variations like `LF` and `low fat` with `Low Fat` for uniformity.  
- **Unifying Outlet Information:** Combined outlet type and size variations into consistent categories.  
- **Handling Missing Values:** Imputed missing `Item Weight` values using mean imputation to maintain realistic averages.  
- **Filtering Invalid Records:** Removed rows with zero visibility or incomplete data that could distort KPIs.  
- **Converting Year Fields:** Converted `Outlet_Establishment_Year` from text to numeric, enabling chronological trend analysis.

<img width="1919" height="1029" alt="Screenshot 2025-07-17 135052" src="https://github.com/user-attachments/assets/e64fab95-f446-4d04-a729-0d2fdeea2871" />


This process transformed an inconsistent raw dataset into a **structured and reliable dataset** suitable for modeling, while ensuring future scalability for periodic updates.

---

## 4. Transformed Data

The output of Power Query was a **clean, structured dataset** with standardized fields and logically ordered columns. Fat content values were now binary (Low Fat vs Standard Fat), outlet sizes were unified into Small, Medium, and Large, and missing weights were filled. Establishment years were numeric, allowing them to be plotted for time-based analysis.

<img width="1632" height="798" alt="Screenshot 2025-07-13 231030" src="https://github.com/user-attachments/assets/71354bea-8984-432b-b6ef-9755c8a4c60d" />


At this stage, the dataset was ready to feed into PivotTables and charts without additional preprocessing. This structured format significantly reduced manual work for every future update.

---

## 5. PivotTables and KPI Modeling

PivotTables served as the analytical engine of the dashboard. They aggregated data across dimensions such as **fat content, product category, outlet size, and location tier**, allowing users to quickly explore trends.

Key KPIs — Total Sales, Average Sales per Item, Total Items Sold, and Average Rating — were calculated here, forming the **top-level metrics** of the dashboard. PivotTables also enabled **dynamic slicing** by filters (e.g., view sales of “Low Fat” items in Tier 3 outlets only).

<img width="1890" height="795" alt="Screenshot 2025-07-13 231103" src="https://github.com/user-attachments/assets/9029b828-4114-47dc-8009-708701330846" />


These PivotTables were linked to visualizations (donut, bar, line charts) and updated in real-time when slicers were used, creating a seamless interactive experience.

---

## 6. Stakeholders

The dashboard was designed with multiple users in mind:  

- **Category Managers** could identify high-performing products and optimize assortments.  
- **Marketing Teams** could analyze customer preferences (e.g., low fat vs standard fat) to design campaigns.  
- **Sales Teams** could track performance by location tier and outlet size to focus efforts on top-revenue contributors.  
- **Operations** could plan logistics and inventory for expanding Tier 3 outlets, which emerged as high-performing segments.

---

## 7. Achievements and Metrics

This project achieved several significant milestones:

- Revealed that **Low Fat products** contributed the majority of sales, influencing Blinkit’s product strategy.  
- Identified **Tier 3 outlets** as unexpected revenue leaders, reshaping regional focus for marketing.  
- Automated data cleaning and KPI calculation, **reducing manual reporting time** by over 70%.  
- Delivered a **360-degree view of sales trends** accessible even to non-technical stakeholders, democratizing insights.

---

## 8. Final Dashboard and Visualization Insights

The final dashboard combined KPIs and multi-type visualizations into a single cohesive view. It offered **real-time interactivity** via slicers, enabling users to explore data across multiple dimensions without technical skills.

<img width="1696" height="713" alt="Screenshot 2025-07-13 001604" src="https://github.com/user-attachments/assets/51fa5934-93b7-42ef-a52b-d7a98a4f94d0" />

### **Key Visuals Explained:**
- **Donut Chart (Fat Content):** Showed Low Fat dominating sales, highlighting a market shift toward healthier products.  
- **Bar Chart (Product Category):** Compared revenue contribution across categories like snack foods, dairy, and beverages.  
- **Line Chart (Establishment Year):** Illustrated sales trends over outlet opening years, revealing growth phases.  
- **Funnel/Map (Location Tier):** Highlighted Tier 3 outlets as surprising leaders in total revenue contribution.  
- **KPI Cards:** Provided quick reference to total sales, average sales, item count, and ratings.

---

## 9. Conclusion

The Blinkit Grocery Sales Analysis Dashboard is a comprehensive example of **end-to-end analytics development** using Excel. From raw data wrangling with Power Query to dynamic visualization with PivotTables and slicers, this project demonstrates how thoughtful design and robust data cleaning can deliver enterprise-level insights using widely accessible tools.

By transforming over 8,500 messy transactional records into an interactive BI solution, this project not only uncovered valuable insights — like the dominance of Low Fat items and Tier 3 outlets — but also provided Blinkit’s teams with a **scalable, refreshable dashboard** to support ongoing strategic decisions. It stands as a testament to my ability to combine **data engineering, analysis, and visualization skills** to deliver actionable business intelligence.

