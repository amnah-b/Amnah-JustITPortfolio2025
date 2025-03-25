# SQL Projects 🛢️

This folder includes SQL queries and projects involving data extraction, transformation, and analysis using databases.  

[📂 View Workbook PDF](https://github.com/amnah-b/Amnah-JustITPortfolio2025/blob/main/SQL_Projects/Data_Technician_Workbook_Week_3.pdf)

## 🔹 Project: Write a essay explaining how you would create a database for a small retail company  

**Context:** Imagine you have been hired by a small retail business that wants to streamline its operations by creating a new database system. This database will be used to manage inventory, sales, and customer information. The business is a small corner shop that sells a range of groceries and domestic products. It might help to picture your local convenience store and think of what they sell. They also have a loyalty program, which you will need to consider when deciding what tables to create.

<h1 align="center">Designing a Database for a Small Corner Shop</h1>


 

Understanding the business requirements: 

The main purpose of the database will be to store and organise data related to inventory, sales transactions and customer information. This will allow the business to streamline its operations, by helping them to track their records.  

The primary user of the database would be the store manager/owner as they will need to monitor stock levels, generate sales reports and track customer information. They will also use it to analyse sales trends and customer behaviours to improve business decisions. Employees will the database to check inventory, update stock levels and input sales data into the system during transactions. 

The data types that would be used in this database are: Numeric (both integer and real), string, date/time and Boolean. The numeric data would be for item quantities, costs and points accrued. The string data would include products and names. Boolean data would be used to check if a customer is a loyalty member. 

 

Designing the database schema: 

Table 1: Inventory - The columns will be Product ID (which will be our primary key), Name, Category, Stock Quantity and Price. 

Table 2:  Customer Information - The columns will be Customer ID (which will be our primary key), Customer Name and Contact Information. 

Table 3: Sales - The columns will be Sales ID (which will be our primary key), Sale Date, Customer ID (which will be our foreign key) and Total Amount.  

Table 4: Sales Details - This will link our Sales and Inventory table. The columns will be SaleDetailsID (which is our primary key), SaleID (which is our foreign key linking to Sales), ProductID (which is our foreign key linking to Inventory), Quantity and Subtotal.  

Table 5: Loyalty Program Table – The columns will be CustomerID (which is our primary key) IsMember (which is our Boolean and will give TRUE/FALSE options for whether or not the customer is a member of our loyalty program) and Points.  

The relationship between the tables is as follows: 

Sales and Customers (One-to-Many) 

A customer can make multiple sales over time. 

A sale is linked to one customer (or NULL for guest checkouts). 

Foreign Key: Sales.CustomerID → Customers.CustomerID 

 

Sales and Sales_Details (One-to-Many) 

A sale can include multiple products. 

The Sales_Details table serves as the bridge between Sales and Products. 

Foreign Key: Sales_Details.SaleID → Sales.SaleID 

 

Products and Sales_Details (One-to-Many) 

Each product can be part of multiple sales. 

The Sales_Details table tracks which products were sold in each transaction. 

Foreign Key: Sales_Details.ProductID → Products.ProductID 

 

Customers and Loyalty_Program (One-to-One) 

A customer has one loyalty program account. 

Foreign Key: Loyalty_Program.CustomerID → Customers.CustomerID 

  

 

Implementing the database: 

To create the database and tables for a small supermarket with a loyalty program, you would first use the CREATE DATABASE command to set up the database. Then, use CREATE TABLE commands to define the Inventory, Customers, Sales, SalesDetails and Loyalty Program tables, specifying appropriate columns and relationships: 

CREATE TABLE Inventory (ProductID INT PRIMARY KEY, Name VARCHAR(100), Category VARCHAR(50), Price DECIMAL(10,2), StockQuantity INT); 

  

CREATE TABLE Customers (CustomerID INT PRIMARY KEY, Name VARCHAR(100), ContactInfo VARCHAR(255)); 

  

CREATE TABLE Sales (SaleID INT PRIMARY KEY, CustomerID INT, SaleDate DATE, TotalAmount DECIMAL(10,2), FOREIGN KEY (ProductID) REFERENCES Products(ProductID), FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)); 

  

CREATE TABLE LoyaltyProgram (CustomerID INT PRIMARY KEY, IsMember BOOLEAN, Points INT, FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID));  

 

When tables have been created, data type can be declared. ‘VARCHAR (255)’ can be used for things like email. This will limit the characters length to 255. Also, values like price can be stored in decimal ‘DECIMAL(10, 2)’. Here we are allowing for up to 10 digits, with 2 decimal places. 

 

 

Populating the Database: 

Once the database structure is in place, initial data needs to be inserted for the system to function properly, using SQL INSERT statements. For example, 

INSERT INTO Inventory (ProductID, Name, Category, Stock Quantity, Price)  
 VALUES (1, Chocolate, ‘Confectionery’, 100, 2.50),   
        (2, 'Croissants', 'Bakery', 50, 1.80),   
        (3, 'Butter', 'Dairy', 75, 3.00);   

INSERT INTO Customers (CustomerID, Customer Name, Contact Information) 
 VALUES (7, 'John Doe', '123-456-7890', 'johndoe@example.com'),   
        (16, 'Jane Smith', '987-654-3210', 'janesmith@example.com');    

INSERT INTO Sales (Customer_ID, Sale_ID, Sale_Date, Total_Amount)   
 VALUES (1, 7, '2025-02-13 10:15:00', 25.00);   

INSERT INTO Sales_Details (Sales_DeatilsID, Sale_ID, Product_ID, Quantity, Subtotal)   
 VALUES (9, 1, 7, 2, 5.00); 

INSERT INTO LoyaltyProgram (CustomerID, IsMember Points) 

VALUES (1, TRUE, 10); 

 

 

Maintaining the database: 

 

To ensure data accuracy and system reliability, we should:  

 
• Take part in regular updates - Implement triggers/stored procedures to automatically adjust inventory levels in response to sales transactions. For example, for inventory management as items are sold, the stock quantities should be updated. Another important piece of information that should be updated is client details, i.e. those most active/still part of loyalty programme. 

  
• Backups - We should have regular backups to prevent data loss, this could be a scheduled daily back up.  

 
• Security Measures – It is crucial to implement user authentication and access controls to prevent changes being made from unknown parties and so that there is restricted access to sensitive information. Also, ensure customer data is encrypted and there are firewalls for protection. 
