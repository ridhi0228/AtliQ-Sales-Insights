[Link to Dashboard](https://www.novypro.com/project/atliq-hardware-sales-insights-1)


# AtliQ-Sales-Insights

AtliQ Hardware
- Is a company which supplies computer hardware and peripherals to many clients across India;
- The company has a head office in Dehli and regional offices throughout India.

Business Issue
The sales director is facing a lot of challenges such as:
The marketing is growing dynamically and then he’s struggling in terms of tracking the sales, needing more accurate insights about the company sales, and then take the necessary decisions.

I used SQL queries in MySQL Workbench to take a look into the data and Power BI for ETL and visualizations to create the insights.

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

 Show total number of customers
       `SELECT count(*) FROM customers;`

 Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

 Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

 Show transactions where currency is US dollars

    SELECT * from transactions where currency="USD"`

 Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

 Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

 Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


![Screenshot (53)](https://github.com/ridhi0228/AtliQ-Sales-Insights/assets/132190698/6694fc95-85a1-4c93-b70a-a0e945292120)



