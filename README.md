# Advanced-Database-Programming-Final-Project

Murach's SQL Server 2019 for Developers: My Guitar Shop Project - CSIS 332

October 21, 2022

Data Files for project can be accessed from Murach's website under "FREE downloads." Concepts of Chapter 2-12 will be recapped.

Instructions for each problem can be seen below. This README is for those that wish to specifically view the questions for the queries divided by chapter.


Chapter 2
How to use the Management Studio
Before you start the exercises…
Before you start these exercises, you need to install SQL Server and the SQL Server Management Studio. The procedures for doing both of these tasks are provided in appendix A of the book.
In addition, you’ll need to get the MGS Exercise Starts directory from your instructor. This directory contains some script files that you need to do these exercises.
Exercises
In these exercises, you’ll use SQL Server Management Studio to create the MyGuitarShop database, to review the tables in the MyGuitarShop database, and to enter SQL statements and run them against this database.

Create the database

1.	Start SQL Server Management Studio and open a connection using either Windows or SQL Server authentication.
2.	Open the script file named CreateMyGuitarShop.sql that’s in the MGS Exercise Starts directory by clicking the Open File button in the toolbar and then using the resulting dialog box to locate and open the file.
3.	Execute the entire script by clicking the Execute button in the SQL Editor toolbar or by pressing F5. When you do, the Messages tab indicates whether the script executed successfully.

Review the database

4.	In the Object Explorer window, expand the node for the database named MyGuitarShop so you can see all of the database objects it contains. If it isn’t displayed in the Object Explorer window, you may need to click on the Refresh button to display it.
5.	View the data for the Categories and Products tables.
6.	Navigate through the database objects and view the column definitions for at least the Categories and Products tables.

Enter and run SQL statements

As you complete the following project you will need to create a Microsoft word document.  This is similar to the chapter exercise document but for this project you will need to add the SQL code for each exercise.  Therefore, this document will contain (1) the Chapter #and  Exercise Step # followed by SQL code for each and (2) the FULL Screen Shot of your query after execution/running with computer date and time showing.

•	Open a blank document in Microsoft Word
•	Save as:  YourFirstName_YourLastName_Database_Project
•	Leave both Management Studio and Word open at the same time.  This will allow for easily coping and pasting both the (1) SQL code and (2) screen captures into the word document.  If an exercise does not require writing code, type N/A where the SQL code would normally be posted.  This word document or converted PDF document will be submitted for grading at the end of the exercises.

7.	Open a new Query Editor window by clicking the New Query button in the toolbar. Then, select the MyGuitarShop database from the Available Databases dropdown menu (Crtl + U) to choose it as the default database.
 
8.	Enter and run this SQL statement:
SELECT ProductName FROM Products
•	In Word Type “chapter 2, step 8”
•	Paste your code into the word document (…Database_Project)
•	Take a Screen Capture, click on the Word Document (…Database_Project), paste the screen capture into the Word Document.  Note:  Do not edit any of the screen capture(s), the screen capture(s) must contain the date and time stamp.  If the capture(s) are edited, the work will NOT be graded.

9.	Delete the e at the end of ProductName and run the statement again. Note the error number and the description of the error.
•	In Word Type “chapter 2, step 9”
•	Paste your code into the word document (…Database_Project)
•	Take a Screen Capture, click on the Word Document (…Database_Project), paste the screen capture into the Word Document.  Note:  Do not edit any of the screen capture(s), the screen capture(s) must contain the date and time stamp.  If the capture(s) are edited, the work will NOT be graded.

10.	Open another Query Editor window and then enter and run this statement:
SELECT COUNT(*) AS NumberOfProducts
FROM Products
•	In Word Type “chapter 2, step 10”
•	Paste your code into the word document (…Database_Project)
•	Take a Screen Capture, click on the Word Document (…Database_Project), paste the screen capture into the Word Document.  Note:  Do not edit any of the screen capture(s), the screen capture(s) must contain the date and time stamp.  If the capture(s) are edited, the work will NOT be graded.

Open and run scripts
11.	Open the script named ProductDetails.sql that’s in the MGS Exercise Starts directory. Note that this script contains just one SQL statement. Then, run the statement.
12.	Open the script named ProductSummary.sql that’s in the MGS Exercise Starts directory. Note that this opens another Query Editor window.
13.	Open the script named ProductStatements.sql that’s in the MGS Exercise Starts directory. Notice that this script contains two SQL statements that end with semicolons.
14.	Press the F5 key or click the Execute button to run both of the statements in this script. Note that this displays the results in two Results tabs. Make sure to view the results of both SELECT statements.
•	In Word Type “chapter 2, step 14”
•	Paste your code into the word document (…Database_Project)
•	Take a Screen Capture, click on the Word Document (…Database_Project), paste the screen capture into the Word Document.  Note:  Do not edit any of the screen capture(s), the screen capture(s) must contain the date and time stamp.  If the capture(s) are edited, the work will NOT be graded.

15.	Exit from SQL Server Management Studio.

Chapter 3
How to retrieve data from a single table
Exercises
Enter and run your own SELECT statements
•	Open the word document from the previous exercise.

In these exercises, you’ll enter and run your own SELECT statements.
1.	Write a SELECT statement that returns four columns from the Products table: ProductCode, ProductName, ListPrice, and DiscountPercent. Then, run this statement to make sure it works correctly.
Add an ORDER BY clause to this statement that sorts the result set by list price in descending sequence. Then, run this statement again to make sure it works correctly. This is a good way to build and test a statement, one clause at a time.
•	In Word Type “chapter 3, step 1”
•	Paste your code into the word document (…Database_Project)
•	Take a Screen Capture, click on the Word Document (…Database_Project), paste the screen capture into the Word Document.  Note:  Do not edit any of the screen capture(s), the screen capture(s) must contain the date and time stamp.  If the capture(s) are edited, the work will NOT be graded.

2.	Write a SELECT statement that returns one column from the Customers table named FullName that joins the LastName and FirstName columns.
Format this column with the last name, a comma, a space, and the first name like this:
Doe, John
Sort the result set by last name in ascending sequence.
Return only the customers whose last name begins with a letter from M to Z.
•	Continue Typing the chapter #, step #, pasting code, and screen captures into the word document as the exercises are completed for this final project.

3.	Write a SELECT statement that returns these column names and data from the Products table:
ProductName	The ProductName column
ListPrice	The ListPrice column
DateAdded	The DateAdded column
Return only the rows with a list price that’s greater than 500 and less than 2000.
Sort the result set in descending sequence by the DateAdded column.

4.	Write a SELECT statement that returns these column names and data from the Products table:
ProductName	The ProductName column
ListPrice	The ListPrice column
DiscountPercent	The DiscountPercent column
DiscountAmount	A column that’s calculated from the previous two columns
DiscountPrice	A column that’s calculated from the previous three columns
Sort the result set by discount price in descending sequence.

5.	Write a SELECT statement that returns these column names and data from the OrderItems table:
ItemID	The ItemID column
ItemPrice	The ItemPrice column
DiscountAmount	The DiscountAmount column
Quantity	The Quantity column
PriceTotal	A column that’s calculated by multiplying the item price by the quantity
DiscountTotal	A column that’s calculated by multiplying the discount amount by the quantity
ItemTotal	A column that’s calculated by subtracting the discount amount from the item price and then multiplying by the quantity
Only return rows where the ItemTotal is greater than 500.
Sort the result set by item total in descending sequence.
Work with nulls and test expressions

6.	Write a SELECT statement that returns these columns from the Orders table:
OrderID	The OrderID column
OrderDate	The OrderDate column
ShipDate	The ShipDate column
Return only the rows where the ShipDate column contains a null value.

7.	Write a SELECT statement without a FROM clause that creates a row with these columns:
Price	100 (dollars)
TaxRate	.07 (7 percent)
TaxAmount	The price multiplied by the tax rate
Total	The price plus tax
To calculate the fourth column, add the expressions you used for the first and third columns.

Chapter 4
How to retrieve data 
from two or more tables
Exercises
1.	Write a SELECT statement that joins the Categories table to the Products table and returns these columns: CategoryName, ProductName, ListPrice.
Sort the result set by CategoryName and then by ProductName in ascending order.

2.	Write a SELECT statement that joins the Customers table to the Addresses table and returns these columns: FirstName, LastName, Line1, City, State, ZipCode.
Return one row for each address for the customer with an email address of allan.sherwood@yahoo.com.

3.	Write a SELECT statement that joins the Customers table to the Addresses table and returns these columns: FirstName, LastName, Line1, City, State, ZipCode.
Code the join so only addresses that are the shipping address for a customer are returned.

4.	Write a SELECT statement that joins the Customers, Orders, OrderItems, and Products tables. This statement should return these columns: LastName, FirstName, OrderDate, ProductName, ItemPrice, DiscountAmount, and Quantity.
Use aliases for the tables.
Sort the final result set by LastName, OrderDate, and ProductName.

5.	Write a SELECT statement that returns the ProductName and ListPrice columns from the Products table.
Return one row for each product that has the same list price as another product. (Hint: Use a self-join to check that the ProductID columns aren’t equal but the ListPrice column is equal.)
Sort the result set by ProductName.

6.	Write a SELECT statement that returns these two columns: 
CategoryName	The CategoryName column from the Categories table
ProductID	The ProductID column from the Products table
Return one row for each category that has never been used. (Hint: Use an outer join and only return rows where the ProductID column contains a null value.)
 
7.	Use the UNION operator to generate a result set consisting of three columns from the Orders table: 
ShipStatus	A calculated column that contains a value of SHIPPED or NOT SHIPPED
OrderID	The OrderID column
OrderDate	The OrderDate column
If the order has a value in the ShipDate column, the ShipStatus column should contain a value of SHIPPED. Otherwise, it should contain a value of NOT SHIPPED.
Sort the final result set by OrderDate.

Chapter 5
How to code summary queries
Exercises
1.	Write a SELECT statement that returns these columns:
The count of the number of orders in the Orders table
The sum of the TaxAmount columns in the Orders table

2.	Write a SELECT statement that returns one row for each category that has products with these columns:
The CategoryName column from the Categories table
The count of the products in the Products table
The list price of the most expensive product in the Products table
Sort the result set so the category with the most products appears first.

3.	Write a SELECT statement that returns one row for each customer that has orders with these columns:
The EmailAddress column from the Customers table
The sum of the item price in the OrderItems table multiplied by the quantiy in the OrderItems table
The sum of the discount amount column in the OrderItems table multiplied by the quantiy in the OrderItems table
Sort the result set in descending sequence by the item price total for each customer.

4.	Write a SELECT statement that returns one row for each customer that has orders with these columns:
The EmailAddress column from the Customers table
A count of the number of orders
The total amount for those orders (Hint: First, subtract the discount amount from the price. Then, multiply by the quantity.)
Return only those rows where the customer has more than 1 order.
Sort the result set in descending sequence by the sum of the line item amounts.

5.	Modify the solution to exercise 4 so it only counts and totals line items that have an ItemPrice value that’s greater than 400.
 
6.	Write a SELECT statement that answers this question: What is the total amount ordered for each product? Return these columns:
The product name from the Products table
The total amount for each product in the OrderItems table (Hint: You can calculate the total amount by subtracting the discount amount from the item price and then multiplying it by the quantity)
Use the ROLLUP operator to include a row that gives the grand total.

7.	Write a SELECT statement that answers this question: Which customers have ordered more than one product? Return these columns:
The email address from the Customers table
The count of distinct products from the customer’s orders

Chapter 6
How to code subqueries
Exercises
1.	Write a SELECT statement that returns the same result set as this SELECT statement, but don’t use a join. Instead, use a subquery in a WHERE clause that uses the IN keyword.
SELECT DISTINCT CategoryName
FROM Categories c JOIN Products p
  ON c.CategoryID = p.CategoryID
ORDER BY CategoryName

2.	Write a SELECT statement that answers this question: Which products have a list price that’s greater than the average list price for all products?
Return the ProductName and ListPrice columns for each product.
Sort the results by the ListPrice column in descending sequence.

3.	Write a SELECT statement that returns the CategoryName column from the Categories table.
Return one row for each category that has never been assigned to any product in the Products table. To do that, use a subquery introduced with the NOT EXISTS operator.

4.	Write a SELECT statement that returns three columns: EmailAddress, OrderID, and the order total for each customer. To do this, you can group the result set by the EmailAddress and OrderID columns. In addition, you must calculate the order total from the columns in the OrderItems table.
Write a second SELECT statement that uses the first SELECT statement in its FROM clause. The main query should return two columns: the customer’s email address and the largest order for that customer. To do this, you can group the result set by the EmailAddress column.

5.	Write a SELECT statement that returns the name and discount percent of each product that has a unique discount percent. In other words, don’t include products that have the same discount percent as another product.
Sort the results by the ProductName column.

6.	Use a correlated subquery to return one row per customer, representing the customer’s oldest order (the one with the earliest date). Each row should include these three columns: EmailAddress, OrderID, and OrderDate.

Chapter 7
How to insert, update, and delete data
Exercises
To test whether a table has been modified correctly as you do these exercises, you can write and run an appropriate SELECT statement.
1.	Write an INSERT statement that adds this row to the Categories table:
CategoryName:	Brass
Code the INSERT statement so SQL Server automatically generates the value for the CategoryID column.

2.	Write an UPDATE statement that modifies the row you just added to the Categories table. This statement should change the CategoryName column to “Woodwinds”, and it should use the CategoryID column to identify the row.

3.	Write a DELETE statement that deletes the row you added to the Categories table in exercise 1. This statement should use the CategoryID column to identify the row.

4.	Write an INSERT statement that adds this row to the Products table:
ProductID:	The next automatically generated ID 
CategoryID:	4
ProductCode:	dgx_640
ProductName:	Yamaha DGX 640 88-Key Digital Piano
Description:	Long description to come.
ListPrice:	799.99
DiscountPercent:	0 (this is the default)
DateAdded:	Today’s date/time.
Use a column list for this statement.

5.	Write an UPDATE statement that modifies the product you added in exercise 4. This statement should change the DiscountPercent column from 0% to 35%.

6.	Write a DELETE statement that deletes the row in the Categories table that has an ID of 4. When you execute this statement, it will produce an error since the category has related rows in the Products table. To fix that, precede the DELETE statement with another DELETE statement that deletes all products in this category.

7.	Write an INSERT statement that adds this row to the Customers table:
EmailAddress:	rick@raven.com
Password:	(empty string)
FirstName:	Rick
LastName:	Raven
Use a column list for this statement.

8.	Write an UPDATE statement that modifies the Customers table. Change the password column to “secret” for the customer with an email address of rick@raven.com.
9.	Write an UPDATE statement that modifies the Customers table. Change the password column to “reset” for every customer in the table.
10.	Open the script named CreateMyGuitarShop.sql that’s in the MGS Exercise Starts directory. Then, run this script. That should restore the data that’s in the database. If an error message is displayed indicating that the database is in use, you’ll need to close and restart the Management Studio and then run the script again.

Chapter 8
How to work with data types
Exercises
1.	Write a SELECT statement that returns these columns from the Products table:
The ListPrice column
A column that uses the CAST function to return the ListPrice column with 1 digit to the right of the decimal point
A column that uses the CONVERT function to return the ListPrice column as an integer
A column that uses the CAST function to return the ListPrice column as an integer

2.	Write a SELECT statement that returns these columns from the Products table:
The DateAdded column
A column that uses the CAST function to return the DateAdded column with its date only (year, month, and day)
A column that uses the CAST function to return the DateAdded column with its full time only (hour, minutes, seconds, and milliseconds) 
A column that uses the CAST function to return the DateAdded column with just the month and day

3.	Write a SELECT statement that returns these colums from the Orders table:
A column that uses the CONVERT function to return the OrderDate column in this format: MM/DD/YYYY. In other words, use 2-digit months and  days and a 4-digit year, and separate each date component with slashes.
A column that uses the CONVERT function to return the OrderDate column with the date, and the hours and minutes on a 12-hour clock with an am/pm indicator.
A column that uses the CONVERT function to return the OrderDate column with just the time in a 24-hour format, including the milliseconds.

Chapter 9
How to work with functions
Exercises
1.	Write a SELECT statement that returns these columns from the Products table:
The ListPrice column
The DiscountPercent column
A column named DiscountAmount that uses the previous two columns to calculate the discount amount and uses the ROUND function to round the result to 2 decimal places

2.	Write a SELECT statement that returns these columns from the Orders table:
The OrderDate column
A column that returns the four-digit year that’s stored in the OrderDate column
A column that returns only the day of the month that’s stored in the OrderDate column
A column that returns the result from adding thirty days to the OrderDate column

3.	Write a SELECT statement that returns these columns from the Orders table:
The CardNumber column
The length of the CardNumber column
The last four digits of the CardNumber column
When you get that working right, add the column that follows to the result set. This is more difficult because the column requires the use of functions within functions.
A column that displays the last four digits of the CardNumber column in this format: XXXX-XXXX-XXXX-1234. In other words, use Xs for the first 12 digits of the card number and actual numbers for the last four digits of the number.

4.	Write a SELECT statement that returns these columns from the Orders table:
The OrderID column
The OrderDate column
A column named ApproxShipDate that’s calculated by adding 2 days to the OrderDate column
The ShipDate column
A column named DaysToShip that shows the number of days between the order date and the ship date
When you have this working, add a WHERE clause that retrieves just the orders for January 2020.

Chapter 10
How to design a database
Exercises
1.	Create a database diagram that shows the relationships between the seven tables in the MyGuitarShop database. (The administrators table is not related to the other six tables.)

2.	Design a database diagram for a database that stores information about the downloads that users make from a website.
Each user must have an email address, first name, and last name.
Each user can have one or more downloads.
Each download must have a filename and download date/time.
Each product can be related to one or more downloads.
Each product must have a name.

Chapter 11
How to create a database and its tables with SQL statements
Exercises
1.	Write a script that adds an index to the MyGuitarShop database for the zip code field in the Addresses table.
2.	Write a script that implements the following design in a database named MyWebDB:
 
In the Downloads table, the UserID and ProductID columns are the foreign keys.
In the Users table, the EmailAddress and LastName columns are required, but the FirstName column is not.
Include a statement to drop the database if it already exists.
Include statements to create and select the database.
Include any indexes that you think are necessary.

3.	Write a script that adds rows to the database that you created in exercise 2.
Add two rows to the Users and Products tables.
Add three rows to the Downloads table: one row for user 1 and product 1; one for user 2 and product 1; and one for user 2 and product 2. Use the GETDATE function to insert the current date and time into the DownloadDate column.
Write a SELECT statement that joins the three tables and retrieves the data from these tables like this:
Sort the results by the email address in descending order and the product name in ascending order.

4.	Write an ALTER TABLE statement that adds two new columns to the Products table created in exercise 2.
Add one column for product price that provides for three digits to the left of the decimal point and two to the right. This column should have a default value of 9.99.
Add one column for the date and time that the product was added to the database.
 
5.	Write an ALTER TABLE statement that modifies the Users table created in exercise 2 so the FirstName column cannot store null values and can store a maximum of 20 characters.
Code an UPDATE statement that attempts to insert a null value into this column. It should fail due to the not null constraint.
Code another UPDATE statement that attempts to insert a first name that’s longer than 20 characters. It should fail due to the length of the column.

Chapter 12
How to create a database and its tables with the Management Studio
Exercises
1.	Use the Management Studio to create a new database named MyWebDB using the default settings. (If the database already exists, use the Management Studio to delete it and then recreate it.)
2.	Use the Management Studio to create the following tables and relationships.
3.	Define the UserID column in the Users table, the ProductsID column in the Products table, and the DownloadID column in the Downloads table as primary keys and identity columns.
4.	In the Downloads table, set the UserID and ProductID columns as the foreign keys.
5.	Define the columns so none of them allow null values.
6.	Use the Management Studio to create indexes for the foreign keys in the Downloads table. 
7.	Use the Management Studio to create a unique index on the EmailAddress and ProductName columns and a regular index on the DownloadDate column.


