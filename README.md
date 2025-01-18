# Sales-Analysis---Walmart

This SQL Data Analysis project, inspired by and following the tutorial of the Youtube Channel [Code with Prince](https://www.youtube.com/watch?v=36fBGMT0tuE) , looks at historical sales data for 45 Walmart stores, provided by the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting). This project aims to examine the provided data, and identify the highest performing branches and products, analyse sales trends across various product lines and times (regarding times of the day, weekdays, months), and gain insights into the quality of service experienced by customers in these stores. 

The SQL queries for this project were written using MySQL Workbench. This project also includes the creation of 3 Tableau dashboards, visualising the provided data to aid in product, customer, and sales analysis.

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
**The coding used to find these results can be found in this file: [WalmartSQLqueries.sql](https://github.com/03LimbuA/Sales-Analysis---Walmart/blob/main/WalmartSQLqueries.sql)**

EXAMPLE OF CODING:
```sql
SELECT 
gender, 
COUNT(*) as gender_cnt
FROM sales
WHERE branch = "A"
GROUP BY gender
ORDER BY gender_cnt DESC;
```

**The full analysis answering the questions below can be found in this file: [analysis walmart word PDF.pdf](https://github.com/03LimbuA/Sales-Analysis---Walmart/blob/main/analysis%20walmart%20word%20PDF.pdf)**

A few examples of the full analysis:
>1. Understanding times that get the most positive/negative ratings can help these Walmart stores identify the time of day when issues are most likely to occur, e.g., staffing needs, product availability. This insight can lead to targeted improvements in the areas during those specific times.
>-	However, the data shows that the time of the day doesn’t seem to affect the quality of the service experienced by customers in these Walmart stores, as each time of the day (morning, afternoon, evening) seem to have similar ratings.
>2. Some businesses, often retailers, use 'member' to distinguish between those who buy regularly from them compared to those who do not.
>-	Customers who are members can bring more revenue than ‘normal’ customers - however, the data shows that there’s no significant difference in the amount of revenue brought by Member customers, compared to Normal/Non-member customers.


### Generic Question
1. How many unique cities does the data have?
2. In which city is each branch?

### Product analysis
1. How many unique product lines does the data have?
2. What is the most common payment method?
3. What is the most selling product line?
4. What is the total revenue by month?
5. What month had the largest COGS?
6. What product line had the largest revenue?
5. What is the city with the largest revenue?
6. What product line had the largest VAT?
7. Which branch sold more products than average product sold?
8. What is the most common product line by gender?
9. What is the average rating of each product line?

### Sales analysis
1. Number of sales made in each time of the day per weekday
2. Which of the customer types brings the most revenue?
3. Which city has the largest tax percent/ VAT (**Value Added Tax**)?
4. Which customer type pays the most in VAT?

### Customer analysis 

1. How many unique customer types does the data have?
2. How many unique payment methods does the data have?
3. What is the most common customer type?
4. Which customer type buys the most?
5. What is the gender of most of the customers?
6. What is the gender distribution per branch?
7. Which time of the day do customers give most ratings?
8. Which time of the day do customers give most ratings per branch?
9. Which day fo the week has the best avg ratings?
10. Which day of the week has the best average ratings per branch?

## Visualising the data

Using Tableau Public, I created 3 dashboards visualising the data, in order to aid in product analysis, sales analysis, and customer analysis.

[Sales Analysis, Tableau](https://public.tableau.com/app/profile/a.l5815/viz/WALMARTSALESANALYSIStableaudashboard/SalesAnalysis)
![Image 17-01-2025 at 20 13](https://github.com/user-attachments/assets/7bade340-d03c-4473-8964-a5371b7acbb0)


[Product Analysis, Tableau](https://public.tableau.com/app/profile/a.l5815/viz/WALMARTPRODUCTANALYSIStableaudashboard/ProductAnalysis?publish=yes)
![Image 17-01-2025 at 18 40](https://github.com/user-attachments/assets/ce071f82-00ef-441f-8476-2db3890cf8f6)


[Customer Analysis, Tableau](https://public.tableau.com/app/profile/a.l5815/viz/WALMARTCUSTOMERANALYSIStableaudashboard/CustomerAnalysis)
![Image 17-01-2025 at 20 12](https://github.com/user-attachments/assets/c12ed145-cbb2-45fc-8a81-e172ad676d42)

