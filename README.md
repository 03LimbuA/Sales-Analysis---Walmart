# Sales-Analysis---Walmart

This Data Analysis project, inspired by and following the tutorial of the Youtube Channel [Code with Prince](https://www.youtube.com/watch?v=36fBGMT0tuE) , looks at historical sales data for 45 Walmart stores, provided by the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting).

This project aims to examine the provided data, and identify the highest performing branches and products, analyse sales trends across various product lines and times (regarding times of the day, weekdays, months), and gain insights into the quality of service experienced by customers in these stores. 

## The Dataset
Official Dataset Source = [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)

I obtained the dataset from the Youtube Channel 'Code with Prince'; it contains historical Walmart sales data from 3 distinct cities/branches. 

| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| invoice_id              | Invoice of the sales made               | VARCHAR(30)    |
| branch                  | Branch at which sales were made         | VARCHAR(5)     |
| city                    | The location of the branch              | VARCHAR(30)    |
| customer_type           | The type of the customer                | VARCHAR(30)    |
| gender                  | Gender of the customer making purchase  | VARCHAR(10)    |
| product_line            | Product line of the product solf        | VARCHAR(100)   |
| unit_price              | The price of each product               | DECIMAL(10, 2) |
| quantity                | The amount of the product sold          | INT            |
| VAT                 | The amount of tax on the purchase       | FLOAT(6, 4)    |
| total                   | The total cost of the purchase          | DECIMAL(10, 2) |
| date                    | The date on which the purchase was made | DATE           |
| time                    | The time at which the purchase was made | TIMESTAMP      |
| payment_method                 | The total amount paid                   | DECIMAL(10, 2) |
| cogs                    | Cost Of Goods sold                      | DECIMAL(10, 2) |
| gross_margin_percentage | Gross margin percentage                 | FLOAT(11, 9)   |
| gross_income            | Gross Income                            | DECIMAL(10, 2) |
| rating                  | Rating                                  | FLOAT(2, 1)    |

## Preparing The Analysis
**DATA WRANGLING :** When creating our table, we put NOT NULL to ensure there are no null values in our database (filtering out null values)
> 1. Build a database 'salesDataWalmart'
> 2. Create table 'sales' and insert the data
> 3. put **NOT NULL** for each field

**FEATURE ENGINEERING :** Generating new columns, regarding time, from existing ones. These new columns will help give insights into which time of the day most sales are made, which weekday each branch is busiest, and which month shows the most sales and profit.
> 1. Creating a new column `time_of_day`, regarding sales in the Morning, Afternoon, Evening. 

> 2. Creating a new column `day_name` regarding sales in which day of the week (Mon, Tue, Wed, Thur, Fri). 

> 3. Creating a new column `month_name` regarding sales in which month (Jan, Feb, Mar).

The table created, including the 3 new columns, can be viewed here: [TABLEwalmartRESULTS.csv](https://github.com/03LimbuA/Sales-Analysis---Walmart/blob/main/TABLEwalmartRESULTS.csv)

## The Analysis
**(The coding used to find these results can be found in this file: [WalmartSQLqueries.sql](https://github.com/03LimbuA/Sales-Analysis---Walmart/blob/main/WalmartSQLqueries.sql)**

How many unique cities in the data?
3 

In which city is each branch located?


![Image 15-01-2025 at 15 47](https://github.com/user-attachments/assets/ebe54f20-002c-4c8f-a404-e20af55b4c55)
