# global-retail-sales-analysis-excel
Global retail sales analysis using Excel, Power Query, Power Pivot, and DAX to uncover revenue drivers, business risks, and the causes behind a major revenue collapse.


## 1. Project Overview

This project investigates a major revenue collapse in a global electronics retail business.

Between **2016 and 2019**, the company experienced rapid expansion, growing revenue from **$6.4M to $17.3M**. However, by **2021 revenue had fallen below $1M**, representing a dramatic reversal in business performance.

Rather than focusing only on the decline itself, this analysis explores whether **early warning signals were already present in the data during the growth phase**.

The objective of this project was to investigate:

- What drove the rapid growth between 2016 and 2019
- Whether structural risks were already visible during the expansion phase
- How customer, product, and geographic dependencies influenced performance
- Why the decline accelerated after 2019

Using **Excel, Power Query, Power Pivot, and DAX**, I built a structured data model and an interactive dashboard to analyze revenue trends, product performance, customer behavior, and geographic market exposure.

The findings suggest that while external shocks may have triggered the decline, **underlying vulnerabilities were already embedded in the company’s business structure long before the collapse became visible.**


## 2. Business Problem

The retailer experienced strong revenue growth for several years before facing a dramatic and unexpected decline after 2019.

While external factors such as global economic disruptions may have contributed to the downturn, a key question remained:

**Were there structural weaknesses in the business model that made the company vulnerable to this collapse?**

To answer this, the analysis focuses on identifying patterns across several dimensions of the business, including:

- Revenue performance over time
- Customer contribution to overall sales
- Product concentration and dependency
- Geographic market exposure



- Seasonal sales patterns

By examining these factors, the goal of the analysis is to determine whether the decline was purely event-driven or whether **underlying risks were already present within the company’s growth structure.**



## 3. Dataset Overview

The dataset used in this project contains six years of transactional sales data from a global electronics retailer operating across multiple international markets.

The data spans **2016 to 2021** and captures detailed records of customer purchases, product sales, and store performance across different regions.

The dataset is composed of multiple tables representing different components of the business:

- **Sales** – the central transactional table containing order-level sales activity, revenue values, and transaction records. This table serves as the **fact table** used to measure overall business performance.
- **Customers** – customer-level information used to analyze purchasing behavior and customer contribution to total revenue.
- **Products** – product catalog data used to evaluate product performance and identify product concentration in sales.
- **Stores** – store location data used to examine geographic distribution of revenue across markets.
- **Exchange_Rates** – currency conversion data used to standardize sales values across international regions.
- **Data_Dictionary** – documentation describing the structure, fields, and definitions used within the dataset.

Using **Power Query**, these tables were cleaned and prepared before being structured into a **star schema data model in Power Pivot**.

In this model:
- The **Sales table functions as the central fact table**
- **Customers, Products, Stores, Date, and Exchange Rates operate as dimension tables**

This structure allows efficient analysis across key business dimensions such as **time, geography, products, and customers**.

With this model in place, the dataset enables deeper investigation into revenue growth patterns, customer contribution to sales, product dependency, geographic market exposure, and seasonal sales behavior.


## 4. Tools & Technologies

This project was developed entirely in Microsoft Excel, using several advanced Excel components to build a structured analytical workflow.

The following tools were used:

Microsoft Excel  
Primary environment used for data analysis, modeling, and dashboard development.

Power Query  
Used to import raw CSV tables, clean the dataset, standardize formats, correct inconsistencies, and prepare the data before modeling.

Power Pivot  
Used to build the relational data model and connect the dataset tables using a star schema structure.

DAX (Data Analysis Expressions)  
Used to create calculated measures such as revenue totals, profit calculations, year-over-year performance, and average order value.

Excel Pivot Tables & Pivot Charts  
Used to perform exploratory analysis and support the dashboard visualizations.

Excel Dashboard Design  
Used to build the final interactive dashboard, including KPI cards, trend charts, product performance visuals, and geographic revenue comparisons.

Together, these tools enabled the construction of a structured analytical model capable of investigating revenue trends, customer behavior, product performance, and geographic market exposure.

## 5. Data Cleaning & Transformation (Power Query)

Before building the data model, the raw dataset required several cleaning and transformation steps to ensure consistency and analytical usability.

Power Query was used as the primary environment for preparing the dataset before loading it into Power Pivot.

The following transformations were performed:

- Imported multiple tables from the dataset into Power Query
- Standardized column data types across tables
- Corrected inconsistent **date formats** and converted them into a unified Excel date format for accurate time-based analysis
- Created a **Date Table** to support time intelligence calculations and enable proper relationships within the data model
- Cleaned **product naming inconsistencies** to simplify product-level analysis
- Removed unnecessary columns and retained only relevant analytical fields
- Identified and handled data errors during transformation
- Verified column structures and ensured tables were ready for relational modeling

These preparation steps ensured that the dataset was clean, structured, and suitable for building a reliable analytical data model.

### Power Query Environment

<img width="958" height="501" alt="power_query_tables" src="https://github.com/user-attachments/assets/572a5150-3100-4fe5-8e37-ef6de7d45ee0" />


## 6. Data Model (Power Pivot)

After the data cleaning process, the tables were loaded into Power Pivot where a relational data model was created to support efficient analytical queries.

The model follows a star schema design, which separates transactional data from descriptive attributes. This structure improves performance and allows flexible analysis across multiple dimensions.

### Fact Table

SalesFact

The Sales table serves as the central fact table containing transactional records including revenue, order details, and customer purchases.

### Dimension Tables

The fact table is connected to several dimension tables that provide descriptive context for analysis:

- CustomersDIM – customer information used to analyze purchasing behavior
- ProductsDIM – product attributes used to evaluate product performance
- StoresDIM – store locations used for geographic analysis
- Exchange_RatesDIM – currency conversion data used to standardize revenue values
- Date Table – custom calendar table used to enable time-intelligence analysis

### Data Model Relationships

Each dimension table is connected to the Sales fact table using primary and foreign key relationships. This structure enables analysis across several analytical perspectives including:

- Revenue trends over time
- Product performance
- Customer purchasing patterns
- Geographic market exposure

- ### Data Model Diagram

<img width="960" height="479" alt="data_model_relationships" src="https://github.com/user-attachments/assets/66644c9a-ba9c-473c-8da7-a1385e56a50c" />

Power Pivot relationship diagram showing the star schema used in the analytical model.

### DAX Measures

<img width="311" height="362" alt="dax_measures" src="https://github.com/user-attachments/assets/3b1722e2-cad6-44f8-9c94-e96d5e0f636f" />

Custom DAX measures were created to calculate key performance metrics such as total revenue, average order value, and year-over-year 


## 7. Analytical Approach

After building the data model in Power Pivot, the analysis focused on investigating how the retailer’s performance evolved over time and identifying structural patterns that could explain both the rapid growth phase and the later collapse.

The analysis examined the business across several key dimensions.

### Revenue and Profit Performance

Revenue and profit trends were analyzed across the six-year period to identify the period of rapid expansion between 2016 and 2019 and the sharp decline that followed. Year-over-year comparisons were used to evaluate how quickly the business scaled and how dramatically performance deteriorated after the peak year.

### Order Volume and Average Order Value

Customer purchasing behavior was examined through order volume and average order value (AOV). While order volume increased significantly during the growth phase, average order value declined steadily. This pattern suggested that revenue growth was increasingly driven by higher transaction volume rather than higher value purchases, indicating potential pressure on long-term revenue quality.

### Product Performance

Product-level analysis was conducted to identify which products generated the largest share of revenue and profit. The results showed that a small number of desktop products consistently dominated sales performance, revealing a strong dependency on a narrow product mix.

### Customer Contribution

Customer-level revenue distribution was analyzed to determine whether the business relied on a few dominant buyers or a broad customer base. The findings showed that even the highest-spending customers contributed only a small percentage of total revenue individually, indicating a fragmented customer structure without strong anchor accounts.

### Geographic Market Exposure

Sales performance across countries was examined to understand how revenue was distributed geographically. The analysis revealed a heavy concentration of revenue in the United States, while other markets such as Germany, the United Kingdom, Canada, and Australia contributed significantly less. This level of geographic dependency increased the company’s exposure to demand fluctuations within a single market.

### Seasonal Sales Patterns

Monthly sales patterns were analyzed to identify recurring seasonal trends. The data showed consistent performance peaks around the beginning and end of the year, with noticeable dips in early spring months. Understanding these seasonal patterns provided context for interpreting fluctuations in annual performance.

By examining these dimensions together, the objective was not only to observe performance trends but to determine whether the company’s growth structure contained underlying vulnerabilities. The analysis ultimately revealed that several structural risks—including declining order value, product concentration, and geographic dependency—were already present during the expansion phase, long before the revenue collapse became visible.



## 8. Key Insights

The analysis revealed that the company’s revenue collapse did not appear suddenly. Several warning signals were already present during the years when the business appeared to be growing.

### Rapid Growth Before the Collapse

Between 2016 and 2019, the retailer experienced strong expansion.

- Revenue increased from $6.4M in 2016 to $17.32M in 2019
- Total orders grew significantly, reaching 9,083 transactions
- Profit also increased steadily during this period

At first glance, these numbers suggested a healthy and expanding business. However, looking deeper into the underlying metrics revealed patterns that raised important questions.

### Revenue Growth Was Driven by Volume, Not Value

While the number of orders increased rapidly, average order value steadily declined, dropping from $2.25K to about $1.91K.

This suggests that the business was growing primarily because customers were placing more orders, not because they were spending more per purchase. Over time, this kind of growth can become fragile because it depends heavily on maintaining high transaction volume.

### Heavy Dependence on a Small Set of Products

Product performance analysis showed that a small group of desktop products consistently generated the largest share of revenue and profit.

This meant that the company’s performance depended heavily on a narrow product mix. If demand for those products weakened, the business would have limited diversification to cushion the impact.

### A Broad but Fragmented Customer Base

Customer-level analysis showed that even the top customers contributed only a small percentage of total revenue individually.

Rather than relying on a few large clients, the business depended on a large number of smaller buyers. While this increases customer diversity, it also means there were no strong anchor customers providing stable revenue streams.

### Geographic Revenue Was Highly Concentrated

Sales performance across countries revealed that the United States generated the majority of total revenue, significantly exceeding contributions from Germany, the United Kingdom, Canada, and Australia.

This level of geographic concentration meant that the company was heavily exposed to changes in demand within a single market.

### The Collapse Followed the Same Structure as the Growth

Revenue began to decline sharply after 2019, falling dramatically by 2021 to below $1M.

Although external events such as global disruptions may have triggered the decline, the data suggests that the business model already contained several structural risks:

- declining average order value during the growth phase  
- strong reliance on a small group of products  
- heavy geographic dependence on a single market  
- lack of dominant anchor customers  

These patterns indicate that the collapse was not purely a sudden shock, but rather the result of vulnerabilities that had been quietly developing during the years of rapid growth.


### Dashboard Overview

<img width="775" height="368" alt="dashboard_overview" src="https://github.com/user-attachments/assets/3d2e21bc-b5f0-4ac0-8147-ab7f91a53dab" />

Interactive Excel dashboard used to analyze revenue, profit, customer activity, product performance, and geographic market exposure.


### Peak Performance Year (2019)

<img width="760" height="367" alt="dashboard_2019_peak" src="https://github.com/user-attachments/assets/ec1f53c0-4375-4ada-991d-de103bc942bf" />
The dashboard shows the retailer's strongest performance year, where revenue peaked at $17.32M with over 9,000 orders.

### Revenue Collapse (2021)

<img width="765" height="366" alt="dashboard_2021_collapse" src="https://github.com/user-attachments/assets/905a386a-2321-4425-ae2a-54a61b9002e7" />

By 2021, revenue had fallen below $1M and total orders dropped dramatically, marking the sharpest decline in the six-year period.



## 9. Dashboard Design

The dashboard was designed to provide a clear and structured view of the retailer’s business performance across revenue, profitability, customer activity, product performance, and geographic markets.

The layout prioritizes high-level performance indicators at the top of the dashboard, followed by supporting charts that explain the drivers behind those metrics.

### KPI Overview

The first section of the dashboard highlights four core performance indicators:

- Total Revenue
- Total Profit
- Total Orders
- Average Order Value (AOV)

These metrics provide an immediate overview of business performance across the entire dataset.

Each KPI card also includes a trend indicator and sparkline chart, allowing quick visual identification of whether performance is improving or declining compared to previous periods. This makes it easier to quickly detect changes in revenue growth, demand patterns, and spending behavior.

### Sales Trend Analysis

A monthly Sales Trend line chart was used to visualize revenue and profit patterns across the year. This chart helps reveal seasonal fluctuations and periods where performance rises or declines.

This visualization supports quick identification of recurring sales patterns and highlights months where performance deviates from the usual trend.

### Product Performance Analysis

Two product-level charts were included:

- Revenue by Product
- Profit by Product

These charts help identify which products contribute the most to overall business performance and reveal whether the company relies on a narrow product mix.

### Customer Contribution

A Top Customers by Revenue chart was included to highlight the highest revenue-generating customers. This helps evaluate the distribution of revenue across customers and determine whether the business relies on a few dominant buyers or a broad customer base.

### Geographic Performance

Revenue and profit were also analyzed across different countries using Revenue by Country and Profit by Country charts.

These visuals help identify geographic concentration and highlight which markets contribute the largest share of business performance.

### Interactive Time Filtering

A timeline slicer was included to allow users to filter the dashboard by year and explore performance changes across the six-year period.

This interactive element enables deeper investigation of specific periods, including the growth phase leading up to 2019 and the decline that followed.

### Dashboard Navigation

Separate worksheet tabs were organized for different analytical views, including:

- KPI calculations
- Pivot chart exploration
- Final dashboard presentation

## 9. Dashboard Design

<img width="775" height="368" alt="dashboard_overview" src="https://github.com/user-attachments/assets/33891bdb-cdea-4181-869f-7e52c2aeaf9a" />

The dashboard was designed to provide a clear and structured view of the retailer’s business performance across revenue, profitability, customer activity, product performance, and geographic markets.


 ## 10. Business Findings

The analysis reveals that the retailer’s revenue collapse was not solely the result of a single external event. Instead, several structural patterns within the business model made the company increasingly vulnerable over time.

### Revenue Growth Was Built on Increasing Order Volume

The company’s growth between 2016 and 2019 was largely driven by a sharp increase in the number of transactions. Total orders rose significantly during this period, allowing revenue to expand rapidly.

However, the data shows that average order value declined steadily, indicating that customers were spending less per transaction. This suggests that the company relied heavily on maintaining high transaction volume to sustain growth.

### Product Sales Were Highly Concentrated

A small group of desktop products consistently generated the highest revenue and profit. While these products performed well during the growth phase, this concentration created significant exposure.

When a business depends heavily on a limited number of products, shifts in demand or changes in technology trends can have a disproportionate impact on overall performance.

### Customer Revenue Was Broad but Fragmented

Customer-level analysis showed that even the highest revenue-generating customers contributed only a small share of total sales individually.

This indicates that the retailer did not have a small set of dominant enterprise customers providing stable, recurring revenue. Instead, performance depended on a large number of smaller purchases spread across many customers.

### Geographic Revenue Was Heavily Concentrated

The majority of revenue came from the United States, while other markets such as Germany, the United Kingdom, Canada, and Australia contributed significantly smaller shares.

This geographic concentration meant that the company’s overall performance was closely tied to demand conditions in a single market.

### Structural Weaknesses Became Visible After 2019

After reaching its peak in 2019, revenue declined sharply over the following two years. Although external disruptions likely played a role in triggering the downturn, the data suggests that the business was already operating with several underlying vulnerabilities:

- declining average order value
- heavy dependence on a small number of products
- strong geographic concentration in one market
- lack of dominant anchor customers

These structural risks meant that once demand conditions changed, the business had limited resilience to absorb the shock.
 ## 11. Recommendations

Based on the patterns observed in the analysis, a few areas stand out where the business model could potentially become more resilient.

### Reduce Dependence on a Narrow Product Mix

The dashboard shows that a small number of desktop products generated a large portion of both revenue and profit. While these products performed strongly during the growth phase, relying heavily on a limited set of products creates risk if demand changes.

From the data, it seems that expanding the product mix or strengthening other product categories could help reduce this dependency.

### Balance Revenue Across More Markets

Sales were heavily concentrated in the United States, while other markets such as Germany, the United Kingdom, Canada, and Australia contributed significantly smaller shares.

If this pattern continued, the company’s performance would remain strongly tied to demand conditions in a single market. Growing sales in other regions could help distribute this risk more evenly.

### Focus on Increasing Order Value

One pattern that stood out in the data was the decline in average order value, even while total orders were increasing. This suggests that growth relied more on transaction volume than on higher-value purchases.

Exploring ways to increase the value of each transaction could potentially strengthen revenue stability.

### Strengthen High-Value Customer Relationships

Customer analysis showed that even the top customers contributed only a small percentage of total revenue individually.

This indicates that the business relied on many smaller purchases rather than a few strong accounts. Building deeper relationships with higher-value customers might help create more stable revenue streams over time.
 ## 12. Limitations of the Analysis

While the analysis reveals several structural patterns in the retailer’s performance, it is important to recognize the limitations of the dataset and the scope of the investigation.

### External Factors Cannot Be Fully Verified

The analysis shows a sharp revenue decline beginning in 2020. While global disruptions such as COVID-19 likely played a role in triggering this downturn, the dataset itself does not contain external economic indicators or operational records that would allow this relationship to be confirmed directly.

As a result, the analysis can highlight patterns in the business performance, but it cannot definitively attribute the decline to a single external cause.

### Operational and Strategic Decisions Are Not Visible

The dataset focuses on sales transactions, customers, products, and stores. However, it does not include information about internal business decisions such as pricing changes, marketing campaigns, inventory shortages, or supply chain disruptions.

These operational factors may have influenced revenue trends but are not observable within the available data.

### Customer Lifecycle Information Is Limited

Customer data allows analysis of purchase activity, but it does not include deeper behavioral signals such as acquisition channels, retention rates, or customer lifetime value.

Because of this, the analysis can identify fragmented customer revenue patterns but cannot fully explain how customer relationships evolved over time.

### Product Strategy Context Is Missing

The data shows that desktop products dominated revenue and profit throughout the analysis period. However, the dataset does not include broader product category information or industry trend data that could explain whether this product mix aligned with changing technology demand in the market.

Despite these limitations, the dataset still provides strong evidence of several structural patterns in the business, including declining average order value, heavy dependence on a small number of products, geographic revenue concentration, and fragmented customer contribution.
## 13. Conclusion

This project began with a simple question: why would a retail business grow rapidly for several years and then experience such a severe collapse?

Between 2016 and 2019, the retailer expanded quickly, growing revenue from $6.4M to $17.3M and more than doubling its order volume. At first glance, the numbers suggested a healthy and rapidly scaling business.

However, a deeper look into the data revealed patterns that made this growth less stable than it appeared.

Average order value was steadily declining, meaning revenue growth relied increasingly on higher transaction volume rather than stronger individual purchases. Product sales were also concentrated around a small group of desktop products, which meant a large share of revenue depended on a limited product mix.

Geographically, the business was heavily dependent on the United States market, which generated the majority of total revenue, while other markets such as Germany, the United Kingdom, Canada, and Australia remained significantly smaller contributors.

Customer analysis also showed that revenue was widely distributed across many customers rather than supported by a few large, stable accounts. This created a structure where performance depended on a constant flow of smaller purchases rather than long-term high-value relationships.

When revenue declined sharply after 2019, these structural weaknesses became more visible. While external disruptions may have triggered the initial downturn, the data suggests the business was already operating with several underlying risks.

Working through this project reinforced an important lesson for me as a junior analyst: strong revenue growth alone does not always indicate a resilient business. Looking deeper into customer behavior, product concentration, geographic exposure, and spending patterns can reveal risks that headline metrics might hide.

This project focused not only on building a dashboard, but on using data to understand how and why business performance changes over time.


## 4. Tools & Technologies

This project was developed entirely in Microsoft Excel, using several advanced Excel components to build a structured analytical workflow.

The following tools were used:

Microsoft Excel  
Primary environment used for data analysis, modeling, and dashboard development.

Power Query  
Used to import raw CSV tables, clean the dataset, standardize formats, correct inconsistencies, and prepare the data before modeling.

Power Pivot  
Used to build the relational data model and connect the dataset tables using a star schema structure.

DAX (Data Analysis Expressions)  
Used to create calculated measures such as revenue totals, profit calculations, year-over-year performance, and average order value.

Excel Pivot Tables & Pivot Charts  
Used to perform exploratory analysis and support the dashboard visualizations.

Excel Dashboard Design  
Used to build the final interactive dashboard, including KPI cards, trend charts, product performance visuals, and geographic revenue comparisons.

Together, these tools enabled the construction of a structured analytical model capable of investigating revenue trends, customer behavior, product performance, and geographic market exposure.
growth.

