### <div align="center"> <h1> E-Commerce Retail Data Analysis </h1> </div>

<p align="center">
  <img src="https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/ab003609-9321-4762-90e0-83d78fd80023" alt="">
</p>

Welcome to EcommerceAnalyticsVault, your premier destination for in-depth e-commerce retail data analysis. This repository is dedicated to uncovering valuable insights and trends within the fast-paced and dynamic world of e-commerce. Leveraging SQL as our primary analytical tool, we embark on a journey to explore customer behavior, sales trends, and product performance, providing actionable insights to drive strategic decision-making in the e-commerce landscape. 

## Tools Used : SQL Server, SSMS
**SQL Server:** A robust relational database management system used for storing, querying, and analyzing large volumes of structured data.

**SQL Server Management Studio (SSMS):** A comprehensive integrated environment for managing SQL Server databases and executing SQL queries, scripts, and procedures.

## Datasets: Customers, Transactions, Prod_cat_info

**Customers:**
Explore comprehensive customer data, including demographics, preferences, and behaviors, to understand the composition and dynamics of the customer base. The Customers table contains comprehensive information about the customers who interact with the e-commerce platform. It serves as a foundational dataset for understanding the demographics, preferences, and behaviors of the customer base. The columns Customer table have are Cusotmer Id, Dob, Gender and City code. The schema for this Customer tables are 4 variables and 5,647 rows.

**Transactions:**
Dive into detailed transaction records to analyze sales performance, product popularity, and purchasing trends over time, providing insights into consumer behavior and market dynamics. The Transactions table contains detailed records of all transactions conducted on the e-commerce platform. It provides valuable insights into sales performance, product popularity, and purchasing trends over time. The columns Transaction table have are transaction id, customer id, date of transaction and etc. The schema for this Transactions table are 10 variables and 23,053 rows.

**Prod_cat_info:**
Gain insights into product categories, assortments, and performance metrics to optimize product offerings, marketing strategies, and inventory management practices. The Prod_cat_info table provides essential information about the products available on the e-commerce platform. It helps categorize products, understand the product assortment, and analyze the performance of different product categories or brands. The columns that have in prod_cat_info tables are prod_cat_code, prod_sub_cat_code, prod_cat and prod_subcat. The schema for this dataset is 4 variables and 23 records

## <div align="center"> <h1> Sql_Project_1 </h1> </div>

**Get Started:**
Ready to dive into the world of e-commerce analytics? Clone the EcommerceAnalyticsVault repository and embark on a journey of exploration, discovery, and innovation in the e-commerce landscape.

### Objectives that Asked

**Data Preparation and Understanding***

Q1. What is the total number of rows in each of the 3 tables in the database?

**Query.**           

SELECT COUNT(*) as Customers FROM Customer
                  
SELECT COUNT(*) as Transactions FROM Transactions
                  
SELECT COUNT(*) as Product_Cat_info FROM prod_cat_info

**Methods Used.**

"SELECT" STATEMENT
                  
"COUNT"  FUNCTION

**Explanation.**

The SQL query consists of three separate "SELECT" statements.
                  
Each "SELECT" statement retrieves data from a different table: "Customer", "Transactions", and "prod_cat_info".
                  
"COUNT(*)" is an aggregate function used to count the number of rows in each table.
                  
The "AS" is a keyword which is used to assign aliases to the count results, making them more readable.
                  
By placing multiple "SELECT" statements in the same script, the SQL engine executes each statement sequentially and returns the results as separate result sets.
                  
This allows you to retrieve counts of rows from multiple tables in a single database round-trip, making the query more efficient compared to executing each "SELECT" statement separately.

**Output**

![Screenshot 2024-05-10 171724](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/a2126eeb-ddcd-4fdd-bb4b-67acaef03c9b)
![Screenshot 2024-05-10 171855](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/99936c77-be05-4736-82bf-ad3347ccb4ca)
![Screenshot 2024-05-10 171758](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/364d88a3-ed82-4214-839b-71c1e35856cc)

Q2. What is the total number of transactions that have a return?

**Query.**

SELECT COUNT(*) as No_of_transactions FROM Transactions
                  
WHERE total_amt < 0

**Methods Used.**

"SELECT" STATEMENT

"COUNT" FUNCTION
				  
"WHERE" CLAUSE

**Explanation.**

The "SELECT" statement is used to retrieve data from the database.
                  
"COUNT(*)" is an aggregate function that counts the number of rows returned by the query.
                  
"FROM Transactions" specifies the table from which to retrieve the data, in this case, the "Transactions" table.
                  
"WHERE" total_amt < 0 is a condition that filters the rows to include only those where the total_amt column has a value less than 0. This condition checks for transactions with negative total amounts, which typically indicates returns or refunds.

**Output**

![Screenshot 2024-05-10 172114](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/6610dfe4-f837-4dca-b095-3911c6019d9a)

Q3. What is the time range of the transaction data available for analysis? Show the output in number of days, months and years simultaneously in different columns.

**Query.**

SELECT
                 
DATEDIFF(DAY, MIN(tran_date), MAX(tran_date)) AS total_days,
                 
DATEDIFF(MONTH, MIN(tran_date), MAX(tran_date)) AS total_months,
                 
DATEDIFF(YEAR, MIN(tran_date), MAX(tran_date)) AS total_years
                 
FROM Transactions

**Methods Used.**

"SELECT" STATEMENT
                 
"DATEDIFF" FUNCTION
				 
"MIN" FUNCTION
				 
"MAX" FUNCTION

**Explanation.**

The "DATEDIFF" function is used three times to calculate the difference between the minimum (MIN(tran_date)) and maximum (MAX(tran_date)) transaction dates.
                 
The first "DATEDIFF" calculates the difference in days (DAY).
                 
The second "DATEDIFF" calculates the difference in months (MONTH).
                 
The third "DATEDIFF" calculates the difference in years (YEAR).
                 
The result of each "DATEDIFF" function call is stored in its respective alias: total_days, total_months, and total_years.
				 
This Query calculates the total number of days, months, and years between the earliest and latest transaction dates in the "Transactions" table, providing insight into the time range covered by the transaction data.

**Output**

![Screenshot 2024-05-10 174019](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/4582083f-573d-47a8-a80d-e08953a7a394)

Q4. Which product category does the sub- category "DIY" belong to?

**Query.**

SELECT * FROM prod_cat_info
		         
WHERE prod_subcat = 'DIY'

**Methods Used.**

"SELECT" STATEMENT
                 
"WHERE" CLAUSE

**Explanation.**

The "SELECT" statement retrieves all columns from the specified table.
                 
The "WHERE" clause filters the rows returned by the query based on a specified condition. In this query, the condition is prod_subcat = 'DIY', which filters the rows to include only those where the value in the "prod_subcat" column is equal to 'DIY'.

**Output**

![Screenshot 2024-05-10 174135](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/fef3eedc-9c43-455f-83cd-2a612144d695)









































































































