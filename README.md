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

**Data Analysis**

Q1. Which channel is most frequently used for transactions?

**Query.**

SELECT TOP 1 Count(*) AS Most_Used, Store_type FROM Transactions
                 
GROUP BY Store_type
	             
ORDER BY Most_Used desc

**Methods Used.**

"SELECT" STATEMENT
                 
"COUNT" FUNCTION
				 
"GROUP BY" CLAUSE
				 
"ORDER BY" CLAUSE

**Explanation.**

The "SELECT TOP 1" statement is used to retrieve only the top 1 row from the result set.
                 
"COUNT(*)" is an aggregate function that counts the number of rows for each group.
                 
"GROUP BY" is a Clause which groups the rows of the "Transactions" table by the values in the "Store_type" column.
                 
"ORDER BY" is a Clause which orders the groups based on the count of rows within each group.
				 
"DESC" is a keyword used in the ORDER BY clause to specify the sort order as descending.
                 
"TOP 1" selects only the first row from the ordered result set, which represents the store type with the highest count of transactions.

**Output**

![Screenshot 2024-05-10 182329](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/e2da6d1a-9a8a-4b74-b7a7-565a762caace)

Q2. What is the count of Male and Female customers in the database?

**Query.**

SELECT Gender, COUNT(*) AS Count FROM Customer
	             
WHERE Gender IS NOT NULL
		         
GROUP BY Gender

**Methods Used.**

"SELECT" STATEMENT
                 
"COUNT" FUNCTION
				 
"WHERE" CLAUSE
				
"GROUP BY" CLAUSE

**Explanation.**

The "SELECT" statement retrieves data from the specified columns in the "Customer" table.
                 
"COUNT(*)" is an aggregate function that counts the number of rows for each group.
                 
"WHERE" is a Clause which filters the rows to include only those where the value in the "Gender" column is not null. This ensures that only customers with a known gender are considered.
                 
"GROUP BY" clause groups the rows of the "Customer" table by the values in the "Gender" column.
                 
Therefore, the query calculates the count of customers for each gender category, grouping the data by gender.

**Output**

![Screenshot 2024-05-10 183534](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/5bb897ba-9187-4f4d-99f4-f26be7fdf9b9)

Q3. From which city do we have the maximum number of customers and how many?

**Query.**

SELECT TOP 1 city_code, COUNT(*) AS Customer_count FROM Customer
                 
GROUP BY city_code
                 
ORDER BY Customer_count DESC

**Methods Used.**

"SELECT" STATEMENT
                 
"COUNT" FUNCTION
				 
"GROUP BY" CLAUSE
				 
"ORDER BY" CLAUSE

**Explanation.**

The SELECT TOP 1 statement is used to retrieve only the top 1 row from the result set.
                 
COUNT(*) AS Customer_count is an aggregate function that counts the number of rows for each group.
                 
The GROUP BY city_code clause groups the rows of the "Customer" table by the values in the "city_code" column.
                 
The ORDER BY Customer_count DESC clause orders the groups in descending order based on the count of customers (Customer_count), with the city code having the highest count appearing first in the result set.
                 
Therefore, the query calculates the count of customers for each city code, grouping the data by city code, and retrieves only the city code with the highest count of customers.

**Output**

![Screenshot 2024-05-10 183909](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/e648f2af-f589-49be-99bb-9e589d939db5)

Q4. How many sub-categories are there under the Books category?

**Query_1**

SELECT COUNT(Distinct prod_subcat) AS sub_cat_count FROM prod_cat_info
                 
WHERE prod_cat = 'Books'
		         
GROUP BY prod_cat

**Query_2**

SELECT Distinct prod_subcat FROM prod_cat_info
                 
WHERE prod_cat = 'Books'

**Methods Used.**

"SELECT" STATEMENT
                 
"COUNT" FUNCTION
				 
"DISTINCT"
				 
"WHERE" CLAUSE
				 
"GROUP BY" CLAUSE

**Explanation.**

The "SELECT" statement retrieves data from the specified columns in the "prod_cat_info" table.
                 
"COUNT" is an aggregate function that counts the number of distinct values in the "prod_subcat" column.
				 
"DISTINCT" is a keyword which is used within the COUNT() function to ensure that only unique values of the prod_subcat column are counted.
                 
"WHERE" clause filters the rows to include only those where the value in the "prod_cat" column is equal to 'Books'. This restricts the count of distinct product subcategories to only those belonging to the "Books" category.
                 
"GROUP BY" clause groups the rows of the "prod_cat_info" table by the values in the "prod_cat" column. Although it's not strictly necessary since there is only one category specified in the WHERE clause, it's included for clarity.
                 
Therefore, the query calculates the count of distinct product subcategories for the "Books" category, grouping the data by the "Books" category.

The first Query only gives us the no. of sub-categories but the second Query gives us the records of the sub-categories.

**Output_1**

![Screenshot 2024-05-10 185957](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/c50e62c3-d327-4ad3-a79f-27fe0d6d8a74)

**Output_2**

![Screenshot 2024-05-10 190136](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/efc2a285-2965-44c1-98fa-b6484ed04b82)

Q5.a. What is the maximum quantity of products ever ordered in a single day?

**Query_1**

SELECT TOP 1 CONVERT(VARCHAR, tran_date, 23) AS DATE, COUNT(Qty) AS Quantity FROM Transactions
                 
GROUP BY tran_date
				 
ORDER BY Quantity DESC

Q5.b. On a Single day, which product was ordered the maximum no. of times

**Query_2**

Select Top 1 Convert(Varchar, T.tran_date, 23) as Date, Count(T.Qty) as Quantity, P.prod_cat, P.prod_subcat from Transactions T
				 
Inner Join prod_cat_info P 
				 
on T.prod_cat_code = P.prod_cat_code and T.prod_subcat_code = P.prod_sub_cat_code
				 
Group By T.tran_date, P.prod_cat, P.prod_subcat
				 
Order By Quantity Desc

**Methods Used.**

"SELECT" STATEMENT
                 
"MAX" FUNCTION

**Explanation.**

"SELECT" statement retrieves data from the specified columns in the "Transactions" table.
        
"MAX" is an aggregate function that calculates the maximum value of the Qty column.
                 
Therefore, the query calculates the maximum value of the Qty column in the "Transactions" table, returning it as "Maximum_Quantity".

**Output_1**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/08d12e51-774e-4889-83d8-d4962f2eeb9c)

**Output_2**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/c5e86bb1-8baf-47a8-880e-e15ea80453ce)

Q6. What is the net total revenue generated in categories Electronics and Books?

**Query**

SELECT SUM(total_amt) AS Total_Revenue, prod_cat FROM Transactions t 
                  
Inner Join prod_cat_info p on t.prod_cat_code = p.prod_cat_code and t.prod_subcat_code = p.prod_sub_cat_code
	              
Group by p.prod_cat
	              
Having p.prod_cat IN ('Electronics', 'Books')

**Methods Used.**

"SELECT" STATEMENT
                  
"SUM" FUNCTION
                  
"JOINS"
				  
"GROUP BY" CLAUSE
				  
"HAVING" CLAUSE

**Explanation.**

"SELECT" statement retrieves data from the specified columns in the "Transactions" table.
                  
"SUM" is an aggregate function used to calculate the total sum of values in the total_amt column of a table.
                  
"Join" used to combine rows from two or more tables based on related columns between them.
                  
"GROUP BY" clause groups the results by the prod_cat column from the "prod_cat_info" table.
                  
"HAVING" clause filters the grouped results to only include rows where the product category is either 'Electronics' or 'Books'.

**Output**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/5fd6fd27-79ac-4c24-81e0-5ff8b2c2d4b2)

Q7. How many customers have >10 transactions with us, excluding returns?

**Query**

SELECT cust_id, COUNT(transaction_id) AS transaction_count FROM Transactions
                  
WHERE total_amt > 0
                  
GROUP BY cust_id
                  
HAVING COUNT(transaction_id) > 10

**Methods Used.**

"SELECT" STATEMENT
                  
"COUNT" FUNCTION
				  
"WHERE"CLAUSE
				  
"GROUP BY" CLAUSE
				  
"HAVING" CLAUSE

**Explanation.**

"SELECT" statement retrieves data from the specified columns in the "Transactions" table.
                  
"COUNT" is an aggregate function that counts the number of non-null values in the transaction_id column for each group.
                  
"WHERE" clause filters the rows to include only those where the value in the total_amt column is greater than 0. This ensures that only transactions with positive total amounts are considered.
                  
"GROUP BY" clause groups the rows of the "Transactions" table by the values in the cust_id column.
                  
"HAVING" clause filters the grouped results to only include rows where the count of transactions for each customer (transaction_id) is greater than 10. This ensures that only customers with more than 10 transactions are included in the result set.

**Output**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/212be8f5-3312-43d0-85ac-1a5da53f219f)

Q8. What is the combined revenue earned from the "Electronics " & "Clothing" categories, from "Flagship stores"?

**Query**

Select round(Sum(total_amt), 2) as combined_revenue, Store_type from Transactions t
	              
Inner join prod_cat_info p on t.prod_cat_code = p.prod_cat_code and t.prod_subcat_code = p.prod_sub_cat_code
                  
Where p.prod_cat IN ('Electronics', 'Clothing')
	              
Group by store_type
	              
Having store_type = 'Flagship store'

**Methods Used.**

"SELECT" STATEMENT
                  
"ROUND" FUNCTION
                  
"SUM" AGGREGATE FUNCTION
				  
"JOINS"
				  
"WHERE" CLAUSE
				  
"GROUP BY" CLAUSE
				  
"HAVING" CLAUSE

**Explanation.**

"SELECT" statement retrieves data from the specified columns in the "Transactions" table.
                  
"ROUND" is a function used to round a numeric value to a specified number of decimal places.
                  
"SUM" is an aggregate function used to calculate the total sum of values in the total_amt column of a table.
                  
"INNER JOIN" used to combine rows from two or more tables based on related columns between them.
                  
"WHERE" clause filters the joined result to include only rows where the prod_cat in the "prod_cat_info" table is either 'Electronics' or 'Clothing'.
                  
"GROUP BY" clause groups the rows of the result set by the store_type column from the "Transactions" table.
                  
"HAVING" clause filters the grouped results to only include rows where the store_type is 'Flagship store'.
                  
Therefore, the query calculates the combined revenue for 'Electronics' and 'Clothing' products sold at 'Flagship store' locations, grouping the results by store type.

**Output**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/0bb81e9f-b582-4117-bdbe-c009832ee501)

Q9. What is the total revenue generated from "Male" customers in "Electronics" category? Output should display total revenue by prod sub-cat.

**Query**

SELECT prod_cat, prod_subcat, SUM(total_amt) AS total_revenue FROM Customer c
                  
JOIN Transactions t ON c.customer_Id = t.cust_id
                  
JOIN prod_cat_info p ON t.prod_cat_code = p.prod_cat_code AND t.prod_subcat_code = p.prod_sub_cat_code
                  
WHERE total_amt > 0 and Gender = 'M'
		          
GROUP BY prod_cat, prod_subcat
		          
Having prod_cat = 'Electronics'

**Methods Used.**

"SELECT" STATEMENT
                  
"SUM" FUNCTION
				  
"JOINS"
				  
"WHERE" CLAUSE
				  
"GROUP BY" CLAUSE
				  
"HAVING" CLAUSE

**Explanation.**

"SELECT" statement retrieves data from the specified columns in the "Transactions" table.
                  
"SUM" is an aggregate function used to calculate the total sum of values in the total_amt column of a table.
                  
"JOIN" used to combine rows from two or more tables based on related columns between them.
                  
"WHERE" clause filters the rows to include only those where total_amt is greater than 0 and Gender is 'M' (for male customers).
                  
"GROUP BY" clause groups the result set by prod_cat and prod_subcat, meaning that the sum of total_amt will be calculated for each unique combination of product category and subcategory.
                  
"HAVING" clause filters the grouped results to include only rows where prod_cat is 'Electronics'.

**Output**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/024886b6-519a-47f0-a47e-08b19176409e)

Q10. What is percentage of sales and returns by product sub catgory; display only top 5 sub categories in terms of sales?

**Query**

Select Top 5 (prod_subcat), Sum(total_amt) as Sales from Transactions t
		          
Inner join prod_cat_info p on t.prod_cat_code = p.prod_cat_code and t.prod_subcat_code = p.prod_sub_cat_code
		          
where t.total_amt > 0
		          
group by prod_subcat
		          
Order by Sales Desc
		 
WITH perABS

as(SELECT TOP 5 (prod_subcat),
		              
    ABS(SUM(CASE WHEN total_amt < 0 THEN total_amt ELSE 0 END)) as Returns,
			          
    SUM(CASE WHEN total_amt > 0 THEN total_amt ELSE 0 END) as Sales
			          
    FROM Transactions t
			          
    INNER JOIN prod_cat_info p on t.prod_cat_code = p.prod_cat_code and t.prod_subcat_code = p.prod_sub_cat_code
			          
    GROUP BY prod_subcat
			          
    ORDER BY Sales DESC)
					  
    SELECT prod_subcat, ROUND((((Returns + Sales)/ Returns)*100), 2) AS Return_percent,
			
    ROUND((((Returns + Sales)/ Sales)*100), 2) AS Sales_percent FROM perABS

**Methods Used.**

"SELECT" STATEMENT
                  
"SUM" FUNCTION
				  
"JOINS"
				  
"WHERE" CLAUSE
				  
"GROUP BY" CLAUSE
				  
"ORDER BY" CLAUSE
				  
"CTE's"

**Explanation.**

**"Main Query"**
                  
"SELECT" statement selects the top 5 prod_subcat values and calculates the sum of total_amt as Sales.
                  
"JOIN" are used to join these tables based on their related columns: prod_cat_code and prod_subcat_code.
                  
"WHERE" clause filters the rows to include only those where total_amt is greater than 0.
                  
"GROUP BY" clause groups the result set by prod_subcat, allowing the calculation of the sum of total_amt for each product subcategory.
                  
"ORDER BY" clause sorts the grouped results by Sales in descending order.
                  
**"Common Table Expression (CTE)":** The query defines a CTE named perABS.
                  
"SELECT" statement within CTE: It selects the top 5 prod_subcat values.
                  
"ABS" and "SUM" :It calculates the absolute sum of quantities for returns and the sum of quantities for sales for each product subcategory.
                  
The "JOIN" are used to join these tables based on their related columns: prod_cat_code and prod_subcat_code.
                  
"GROUP BY" clause within CTE: It groups the result set by prod_subcat, allowing the calculation of returns and sales for each product subcategory.
                  
"ORDER BY" clause within CTE: It sorts the grouped results by Sales in descending order.
                  
The CTE is first evaluated to obtain the returns and sales for the top 5 product subcategories.
                  
Then, the main query selects data from the CTE and calculates the percentages.
                  
The percentages are calculated using the formula: (Returns or Sales / (Returns + Sales)) * 100.
                  
The ROUND function is applied to round the calculated percentages to two decimal places.

**Output_for_Main Query**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/9ffd228d-c884-4e20-8f18-c39977515179)

**Output_for_CTE**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/19e2418a-02bc-4f53-82dc-9946ed19e4aa)

Q11. For all customers aged between 25 to 35 years find what is the net total revenue generated by these consumers in last 30 days of transactions from max transaction date available in the data?

**Query**

SELECT TOP 30 Convert(Varchar, tran_date, 23) AS Max_Transaction_Date FROM Transactions
			       
GROUP BY tran_date
			       
ORDER BY tran_date DESC

WITH ABC

AS(SELECT TOP 30 (tran_date), SUM(total_amt) AS Total_amount FROM Customer c
			       
    INNER JOIN Transactions t ON t.cust_id = c.customer_id
			       
    WHERE DATEDIFF(YEAR,DOB,GETDATE()) BETWEEN 25 AND 35
			       
    GROUP BY tran_date
			       
    ORDER BY tran_date DESC)
			       
    SELECT SUM(Total_amount) AS Final_revenue FROM ABC

**Methods Used.**

"SELECT" STATEMENT
                   
"SUM" FUNCTION
				   
"WHERE" CLAUSE
				   
"GETDATE" FUNCTION
				   
"GROUP BY" CLAUSE
				   
"ORDER BY" CLAUSE
				   
"DATEDIFF" FUNCTION
				   
"MAX" FUNCTION

**Explanation.**

**"Main Query":**
                   
It selects the top 30 distinct tran_date values from the "Transactions" table.
                   
The GROUP BY clause ensures that only distinct tran_date values are returned.
                   
The ORDER BY clause orders the results by tran_date in descending order.
                   
**"Common Table Expression (CTE)":** The query defines a CTE named ABC.
                   
The CTE calculates the total amount for each of the top 30 tran_date values.
                   
It selects the top 30 distinct tran_date values from the "Transactions" table.
                   
It joins the "Customer" and "Transactions" tables based on the customer ID (cust_id) to obtain the total amount for each transaction date.
                   
It filters the customers based on their age, selecting only those aged between 25 and 35 years.
                   
The GROUP BY clause groups the results by tran_date, aggregating the total amount for each transaction date.
                   
The ORDER BY clause orders the results by tran_date in descending order.
                   
**"Final Query":**
                   
It calculates the sum of the Total_amount column from the CTE ABC.
                   
This gives the final revenue generated from transactions corresponding to the top 30 transaction dates involving customers aged between 25 and 35 years.

**Output_for_Main Query**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/11e8cb31-5616-46d7-9760-f2ffb9e19d8a)

**Output_for_CTE**

![image](https://github.com/Swagath123Koyada/EcommerceAnalyticsVault/assets/164196153/9b1841d3-ba23-4c9d-88a0-7004164f9614)










































































