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

Custom DAX measures were created to calculate key performance metrics such as total revenue, average order value, and year-over-year growth.

