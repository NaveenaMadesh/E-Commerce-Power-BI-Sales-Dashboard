# E-Commerce Sales Analysis Dashboard

A Power BI dashboard built on an e-commerce sales dataset. This project covers data cleaning, data modeling using a star schema, and a three page interactive dashboard that analyzes sales performance across time, products, and geography.

## About the Dataset

The raw dataset contains transaction level data from an online retail business. Each row in the dataset represents one product line from a single invoice.

Total records before cleaning: 5,81,587
Total columns: 8

The columns in the raw dataset are invoice number, product code, product description, quantity, unit price, invoice date, customer ID, and country.

## Data Cleaning Process

- Fixed column headers and set correct data types for each column
- Removed extra spaces around text values
- Removed rows with blank product description (1,454 rows removed)
- Standardized country names, EIRE to Ireland and RSA to Russia
- Added Total Sales column, calculated as Quantity multiplied by Unit Price
- Added Invoice Cancellation column
- Added Time column, separated from the original date and time value
- Added Time Category column, grouping transactions into time blocks
- Removed exact duplicate rows (5,270 rows removed)
- Removed non-product records such as postage, dotcom postage, discounts, manual entries, samples, bank charges, amazon fees, and charity commission (2,900 rows removed)
- Removed zero and negative priced rows representing stock adjustments such as damaged, found, and thrown away (9,716 rows removed)

### Final Result

Raw dataset row count: 5,81,587 (Note: this project references 541,909 rows in the working file. Please confirm which figure is correct before finalizing this document.)
Final cleaned dataset row count: 522,569
Total rows removed: 19,340
Percentage of data removed: 3.57 percent
Percentage of data kept: 96.43 percent

## Data Modeling

The cleaned data was organized into a star schema for better performance and easier analysis in Power BI. Dimension tables were derived from the main transaction table, and a fact table was kept at the center of the model.

Tables derived from the E-commerce transaction table:

- Product_Dim
- Geography
- Date
- Cancelled Invoices

These dimension tables are connected to the central transaction (fact) table through primary key and foreign key relationships, following a standard star schema design. This keeps the model simple, avoids repeated data, and allows fast filtering across all dashboard pages.

## Dashboard Pages and Questions Answered

The dashboard has three pages. Each page is designed to answer a specific set of business questions.

### Page 1: Trend Analysis

1. What is the KPI trend across 13 months, and what is the product category level composition within that trend.
2. What is the KPI trend across 4 weeks, specifically at the product category level.
3. What is the KPI trend at the day and time level, specifically at the product category level.

### Page 2: Product Wise Analysis

1. What is the percentage sales contribution of each product category.
2. What are the top performing and worst performing products across all KPIs.
3. What does the cancelled items data show.

### Page 3: Country Wise Analysis

1. What is the individual region level and country level data for all KPIs.
2. What are the top and worst performing countries, in general and specifically within each region, across all KPIs.

## Insights

### Overall KPIs

Total Sales: The e-commerce business generated around 10.25M in revenue.
Total Orders: 523K orders were placed.
Total Quantity: 6M units were sold.
Total Customers: 4K customers made purchases.

These overall numbers do not have a solid reference point to compare against on their own. Additional data such as a previous year or an industry benchmark would be needed to judge whether these numbers are good or bad in a wider context. However, the available one year of data can still be broken down and compared across different time scales, categories, and countries, which is what the rest of this analysis focuses on.

### Time Level Analysis

Month wise analysis:

1. Looking at the monthly trend line, sales were highest in November. Within November, a gradual growth was noticed from week 1 to week 2, but a sudden drop was seen in week 3. This drop needs further analysis to understand the cause and find ways to improve sales during that period. At the hourly level, sales were highest between 9 AM and 6 PM, though the difference between hours in this range is small, close to a 0.2 gap.

2. From September onward, a gradual and noticeable increase in sales can be seen.

3. From May to August, sales stayed close to the average, without major highs or lows.

4. From January to May, sales were unstable and stayed below the average.

Summary of month wise analysis: strong sales growth begins from August. Average sales are maintained from May to August. The first four months of the year show unreliable and below average sales performance.

Week level analysis:

Week 1 and Week 2 tend to perform well within a given month.

Time of day analysis:

Sales perform well between 9 AM and 3 PM.

Category level analysis:

The General or Other category, along with Storage, contributes a relatively high percentage of overall sales. Other categories appear to be purchased only when specifically needed, rather than on a regular basis.

Category level and country level top and bottom performers, across all KPIs, can be analyzed directly in the dashboard on the Product Wise Analysis and Country Wise Analysis pages.

## Files in This Repository

- E-Commerce Sales Dashboard .pbix
- E-Commerce Sales Dashboard. .pdf
- Dashboard_Theme.json
- Data Mondel.png

The original source data file is not included in this repository due to file size limitations.
