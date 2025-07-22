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
