AtliQ Mart – Festival Promotions Analysis

Business Context
AtliQ Mart is a retail giant with over 50 supermarkets in the southern region of India. All their 50 stores ran a massive promotion during Diwali 2023 and Sankranti 2024 on their AtliQ branded products. These promotions aimed to boost sales and enhance customer engagement during significant cultural celebrations. The Sales Director, Bruce Haryali, requires insights into which promotions performed well and which ones fell short to optimize future promotional efforts.

Business Problem
The primary business problem is to analyze the effectiveness of Diwali 2023 and Sankranti 2024 promotions on AtliQ branded products across all 50 AtliQ Mart stores in South India. This involves:

Understanding sales performance metrics

Identifying successful promotional strategies

Determining customer preferences

The objective is to provide insights to the Sales Director to optimize future promotional activities and drive sales growth.

Steps Followed
Loaded the dataset (.csv file) into Power BI Desktop

Opened Power Query Editor and enabled Column Distribution, Column Quality, and Column Profile

Adjusted profiling settings to use the entire dataset

Verified there were no errors or missing values across columns

Applied a visual theme in Report View

Built data relationships between all tables in Model View with proper cardinality and cross-filter direction

Created the Store Performance Analysis report

Key Visuals and Measures
Slicers: Country, Promotion Type

Total Stores

DAX
Total Stores = COUNTROWS(dim_stores)
Total Revenue Before Promotions

DAX
Total_Rev_Before = fact_events[base_price] * fact_events[quantity_sold_before_promo]
Total Revenue After Promotions

DAX
Total_Rev_After = fact_events[base_price] * fact_events[quantity_sold_after_promo]
Incremental Revenue (IR)

DAX
IR = (fact_events[quantity_sold_after_promo] * fact_events[base_price]) 
     - (fact_events[quantity_sold_before_promo] * fact_events[base_price])
Total Sold Units Before Promotion

DAX
Total Sold Unit Before = SUM(fact_events[quantity_sold_before_promo])
Total Sold Units After Promotion

DAX
Total Sold Unit After = SUM(fact_events[quantity_sold_after_promo])
Incremental Units Sold (ISU)

DAX
ISU = fact_events[quantity_sold_after_promo] - fact_events[quantity_sold_before_promo]
Visualizations Included:

Bar chart: Revenue before vs after promotions by City

Top 5 stores by Incremental Revenue

Bottom 5 stores by Incremental Revenue

Published the report to Power BI Service

<img width="593" height="328" alt="image" src="https://github.com/user-attachments/assets/d8ca7157-dca8-4172-af8e-346c30b1cc33" />

Snapshot of Dashboard (Power BI Service)
<img width="1900" height="896" alt="image" src="https://github.com/user-attachments/assets/cda47ce8-c998-48c4-b1ac-96d16bb8ae6e" />

Report Snapshot (Power BI DESKTOP)
<img width="1374" height="775" alt="image" src="https://github.com/user-attachments/assets/dc869321-134d-4f99-a18e-cd263f1c960c" />

Insights
A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

Total Number of Stores = 50
Total Revenue Before Promotions = 141 M

Total Revenue After Promotions = 348 M

Incremental Revenue After the promotion = 207 M

Revenue increased from 141M to 348M after the promotion, showing a 147% growth.

Bengaluru led in revenue, with 32.94M before the promotion, making up 23.41% of total revenue.

Trivandrum had the lowest pre-promotion revenue at 3.2M, 928.90% lower than Bengaluru.

Revenue before and after the promotion showed a strong positive correlation, indicating that stores with higher initial revenue also performed well post-promotion.

Bengaluru saw the highest absolute revenue growth, with an increase of 50.76M after the promotion, highlighting its strong market response.



