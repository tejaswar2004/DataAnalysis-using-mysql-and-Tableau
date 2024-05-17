### About Project
- Performed India based hardware company sales insights - A Data Analysis project.

- Developed ETL mappings using SQL to extract the data from unstructured data and transformed it to the staging area to conduct data cleaning and design star schema data model on Tableau.

- Developed a Tableau dashboard to perform analysis, producing quantitative visualizations in Tableau to draw valuable insights based on different parameters affecting the company performance year on year and further provide business solutions.

## Technologies used

* <a href="https://coursera.org/share/064db4645159df788ad0b31abebf1556">Advance Excel</a><a href="https://coursera.org/share/064db4645159df788ad0b31abebf1556" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/mrankitgupta/66DaysOfData/60139fb461ef56a19afd68ea4094f6069f27ce49/icons8-microsoft-excel%20(1).svg" alt="excel" width="25" height="25"/> </a>

* <a href="https://www.mysql.com/">MySQL</a><a href="https://www.mysql.com/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="35" height="20"/> </a>   |  <a href="https://www.microsoft.com/en-us/sql-server">SQL Server</a><a href="https://www.microsoft.com/en-us/sql-server" target="_blank" rel="noreferrer"> <a href="https://www.microsoft.com/en-us/sql-server" target="_blank"> <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" alt="sql-server" width="28" height="22"/> </a> 

* <a href="https://public.tableau.com/app/profile/mrankitgupta">Tableau</a><a href="https://public.tableau.com/app/profile/mrankitgupta" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/mrankitgupta/mrankitgupta/a768d6bf0a001f03327578ae12f8867e4056cbaf/tableau-software.svg" alt="tableau" width="20" height="20"/> </a>  |
<a href="https://powerbi.microsoft.com/en-us/">Power BI</a><a href="https://powerbi.microsoft.com/en-us/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/mrankitgupta/mrankitgupta/a768d6bf0a001f03327578ae12f8867e4056cbaf/power-bi.svg" alt="powerbi" width="20" height="20"/> </a>

* <a href="https://github.com/mrankitgupta/Statistics-for-Data-Science-using-Python">Statistics</a><a href="https://github.com/mrankitgupta/Statistics-for-Data-Science-using-Python" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/mrankitgupta/66DaysOfData/c8c040f1c85d921db317152567f331354446286a/statistics-21.svg" alt="Statistics" width="25" height="25"/> </a>


## Project - India based Hardware company Sales Insights - Data Analysis performed on Tableau & SQL

### Problem Statements
Sales director wants to know the performance of the company in various Indian states & accordingly provide some discount.

- Q1. Revenue breakdown by cities.

- Q2. Revenue brekdown by years & months.

- Q3. Top 5 customers by revenue & sales quantity.

- Q4. Top 5 Products by revenue.
  
- Q5. Net Profit & Profit Margin by Market
### Setup Process
  
Step 1: Download file: <code>[db_dump.sql](https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/Databases/db_dump.sql)</code> or <code>[db_dump.xlsx](https://github.com/mrankitgupta/Sales-Insights-Data-Analysis-using-Tableau-and-SQL/blob/main/Databases/db_dump.xlsx)</code>

Step 2: Import it in MySql do ETL(Extract, Transform, Load) if required

Step 3: Download [Tableau Public](https://www.tableau.com/products/public/download) (Free) or [Tableau Desktop](https://www.tableau.com/products/desktop/download) (14 days trial) to perform Data Analysis
  
Step 4: Connect Tableau with MySql database or Excel database
  
Step 5: Save the file as (.twb or .twbx)

  
## Data Analysis Using SQL
  
1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001)

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai.

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars.

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table.

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai.

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020and transactions.market_code="Mark001";`
