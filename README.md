Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer shopping patterns across demographics, product categories, discounts, shipping preferences, and subscription status. The project uses Python, PostgreSQL/SQL, and Power BI to turn transactional data into business insights and recommendations.
Business Problem
The retail business wants to understand what influences customer purchasing behavior so it can improve sales, customer engagement, satisfaction, and long-term loyalty.

Key question: How can the company use shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?

Project Objectives

- Clean and prepare the customer shopping dataset.
- Analyze revenue, product ratings, discount behavior, shipping preferences, and subscriptions using SQL.
- Segment customers using purchase history.
- Build an interactive Power BI dashboard.
- Communicate findings and practical recommendations in a report and presentation.
Dataset
File: customer_shopping_behavior.csv
- Records: 3,900
- Columns: 18
- Missing values: 37 values in Review Rating (as documented in the project report)
The dataset includes:
Area	Example fields
Customer profile	Customer ID, Age, Gender, Location
Product and purchase	Item Purchased, Category, Purchase Amount (USD), Size, Color, Season
Customer behavior	Subscription Status, Previous Purchases, Frequency of Purchases
Purchase experience	Review Rating, Shipping Type, Discount Applied, Promo Code Used, Payment Method


Tools and Technologies
- Python: pandas for data loading, exploration, cleaning, and feature engineering
- Jupyter Notebook: step-by-step exploratory analysis
- PostgreSQL / SQL: business-focused queries and aggregation
- Power BI: interactive customer behavior dashboard
- PowerPoint and PDF: presentation and project report
- 
Project Workflow

1. Data preparation in Python
The notebook documents the following workflow:
1. Load the CSV with pandas.
2. Inspect data types, structure, and summary statistics.
3. Check missing values.
4. Impute missing Review Rating values using the median rating for the relevant product category, as described in the report.
5. Standardize column names to snake_case.
6. Create features such as age_group and purchase_frequency_days.
7. Check whether Discount Applied and Promo Code Used are redundant; the report says promo_code_used was dropped.
8. Load the cleaned data into PostgreSQL for SQL analysis.
2. Business analysis in SQL
   
The SQL file contains queries for these business questions:

1. Total revenue by gender
2. Customers who used discounts but spent at least the average purchase amount
3. Five products with the highest average review ratings
4. Average purchase amount for Standard vs. Express shipping
5. Average spend and total revenue for subscribers vs. non-subscribers
6. Products with the highest percentage of discounted purchases
7. Customer segmentation into New, Returning, and Loyal
8. Top three products within each category
9. Subscription status among repeat buyers with more than five previous purchases
10. Revenue contribution by age group
    
3. Power BI dashboard
   
File: customer_behavior_dashboard.pbix

The report presents KPIs and breakdowns such as customer count, average purchase amount, average review rating, subscription status, revenue and sales by category, and revenue/sales by age group. Open the PBIX file in Power BI Desktop to explore the dashboard and its filters.

4. Reporting and presentation
   
- Customer Shopping Behavior Analysis.pdf — project report
- Customer-Shopping-Behavior-Analysis.pptx — presentation
- Business Problem  Document.pdf — original business problem statement
Selected Findings Documented in the Report
The report records these results from the SQL analysis:
- Revenue by gender: Female revenue was reported as 75,191, and male revenue as 157,890.
- Average purchase amount by shipping type: Standard shipping 58.46; Express shipping 60.48.
- Subscription comparison: Subscribers — 1,053 records, average spend 59.49, total revenue 62,645. Non-subscribers — 2,847 records, average spend 59.87, total revenue 170,436.
- Highest discount rates by product: Hat (50.00%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), and Pants (47.37%).
- Customer segments: Loyal 3,116, New 83, Returning 701, using the segmentation logic in the SQL file.
- Revenue by age group: Young Adult 62,143; Middle-aged 59,197; Adult 55,978; Senior 55,763.
These values are reproduced from the project report and should be validated against the final database/dashboard before being used for business decisions. In particular, the presentation contains some claims that do not align clearly with the SQL result tables, so the source of truth should be the executed queries and validated dashboard.

Business Recommendations

The project proposes the following actions:

- Grow subscriptions: Test subscriber-only benefits and measure conversion and retention.
- Strengthen loyalty: Reward repeat purchases and design campaigns to move new customers toward returning and loyal behavior.
- Manage discounts carefully: Evaluate whether discount-driven purchases improve revenue and margin, rather than optimizing only for discount usage.
- Promote strong products: Feature well-rated and frequently purchased products in campaigns.
- Target campaigns thoughtfully: Use customer segments, age groups, product categories, and shipping preferences to personalize marketing.
- Measure outcomes: Track conversion, repeat purchase rate, average order value, revenue, and margin after each campaign.
Repository Structure
Keep the project files organized in a structure like this:
customer-shopping-behavior-analysis/
├── README.md
├── customer_shopping_behavior.csv
├── Customer_Shopping_Behavior_Analysis.ipynb
├── customer_behavior_sql_queries.sql
├── customer_behavior_dashboard.pbix
├── Business Problem  Document.pdf
├── Customer Shopping Behavior Analysis.pdf
└── Customer-Shopping-Behavior-Analysis.pptx

How to Run
Python analysis

1. Install Python and Jupyter Notebook.
2. Install pandas:
   pip install pandas jupyter
3. Place the CSV and notebook in the same directory.
4. Open the notebook and run the cells in order.
   
SQL analysis

1. Set up PostgreSQL.
2. Load the cleaned dataset into a table named customer (the supplied SQL queries expect this table and the standardized column names).
3. Run customer_behavior_sql_queries.sql in a PostgreSQL client such as pgAdmin or DBeaver.
4. Review the outputs and compare them with the report/dashboard.
   
Power BI

1. Open customer_behavior_dashboard.pbix in Power BI Desktop.
2. If prompted, update the data source path or database connection.
3. Refresh the data and validate the displayed KPIs and visuals.
   
Notes and Limitations

- The provided dataset contains purchase records; conclusions describe patterns in this dataset and do not, by themselves, establish causation.
- Revenue totals and average purchase amounts are expressed in the dataset's purchase currency, documented as USD.
- The report describes the Review Rating missing-value treatment and feature engineering; rerun the notebook to verify the final transformed schema.
- The reported gender insight in the presentation conflicts with the revenue totals shown in the report's SQL output. Validate the query output before presenting that conclusion.
- The dataset has no explicit transaction date field listed in the report's feature summary, so time-series or seasonal conclusions should be limited to the fields actually available.

  License
No license is specified. Add a license file if you intend to permit reuse of this project
