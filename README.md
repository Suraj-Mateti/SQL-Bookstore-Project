# 📚 Online Bookstore Database Management (SQL Project)

## 📝 Short Description
A PostgreSQL-based **Online Bookstore Database Project** that includes database schema design, data import from CSV files, and SQL queries for managing books, customers, and orders.  
It also features **advanced SQL queries** to analyze revenue, customer spending, stock management, and best-selling books. Perfect for learning **SQL, Joins, Aggregations, and Database Management**.

---

## 📌 Project Overview
This project is an **Online Bookstore Database Management System** built using **PostgreSQL**.  
It demonstrates **database design, data import, and SQL queries** to manage books, customers, and orders efficiently.  
The project also includes advanced SQL queries for **business insights** such as revenue calculation, top customers, and best-selling books.

---

## ⚙️ Features
- Database schema design for:
  - **Books**
  - **Customers**
  - **Orders**
- Data import using **CSV files**
- SQL queries for:
  - Basic retrieval (books, customers, orders)
  - Filtering and aggregation
  - Joins between multiple tables
  - Business insights (sales, revenue, most ordered book, etc.)
- Stock calculation after fulfilling all orders

---

## 🗂️ Database Schema
### 1. Books Table
| Column         | Type             | Description |
|----------------|------------------|-------------|
| Book_ID        | SERIAL (PK)      | Unique book ID |
| Title          | VARCHAR(100)     | Book title |
| Author         | VARCHAR(100)     | Author name |
| Genre          | VARCHAR(50)      | Genre/category |
| Published_Year | INT              | Year published |
| Price          | NUMERIC(10,2)    | Book price |
| Stock          | INT              | Available stock |

### 2. Customers Table
| Column       | Type             | Description |
|--------------|------------------|-------------|
| Customer_ID  | SERIAL (PK)      | Unique customer ID |
| Name         | VARCHAR(100)     | Customer name |
| Email        | VARCHAR(100)     | Email address |
| Phone        | VARCHAR(15)      | Phone number |
| City         | VARCHAR(50)      | City |
| Country      | VARCHAR(150)     | Country |

### 3. Orders Table
| Column       | Type             | Description |
|--------------|------------------|-------------|
| Order_ID     | SERIAL (PK)      | Unique order ID |
| Customer_ID  | INT (FK)         | References Customers(Customer_ID) |
| Book_ID      | INT (FK)         | References Books(Book_ID) |
| Order_Date   | DATE             | Date of order |
| Quantity     | INT              | Quantity ordered |
| Total_Amount | NUMERIC(10,2)    | Total cost |

---

## 📊 Example Queries
- **Retrieve all books in Fiction genre**
```sql
SELECT * FROM Books WHERE Genre = 'Fiction';
Find the most expensive book

SELECT * FROM Books ORDER BY Price DESC LIMIT 1;


Total revenue generated

SELECT SUM(Total_Amount) AS Revenue FROM Orders;


Most frequently ordered book

SELECT o.Book_ID, b.Title, COUNT(o.Order_ID) AS Order_Count
FROM Orders o
JOIN Books b ON o.Book_ID = b.Book_ID
GROUP BY o.Book_ID, b.Title
ORDER BY Order_Count DESC
LIMIT 1;

🚀 How to Run

Clone the repository:

git clone https://github.com/yourusername/Online-Bookstore-SQL-Database.git
cd Online-Bookstore-SQL-Database


Open PostgreSQL and create the database:

CREATE DATABASE OnlineBookstore;
\c OnlineBookstore;


Run the SQL script (bookstore.sql) to create tables and import data.

Explore the queries inside queries.sql for insights.

📈 Insights from Advanced Queries

Total revenue generated from orders

Top 3 most expensive Fantasy books

Customers with at least 2 orders

Remaining stock after fulfilling all orders

Cities with customers who spent more than $30

🛠️ Tech Stack

Database: PostgreSQL

Data Import: CSV files

Queries: SQL (DDL, DML, Joins, Aggregations)

📄 License

This project is for educational purposes only. Feel free to use and modify.

👨‍💻 Author: Suraj Mateti
🔗 GitHub: 
