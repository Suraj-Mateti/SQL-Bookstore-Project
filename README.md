# 📚 Online Bookstore Database Management (SQL Project)

## 📊 Example Queries
- **Retrieve all books in Fiction genre**
```sql
SELECT * FROM Books WHERE Genre = 'Fiction';
```

- **Find the most expensive book**
```sql
SELECT * FROM Books ORDER BY Price DESC LIMIT 1;
```

- **Total revenue generated**
```sql
SELECT SUM(Total_Amount) AS Revenue FROM Orders;
```

- **Most frequently ordered book**
```sql
SELECT o.Book_ID, b.Title, COUNT(o.Order_ID) AS Order_Count
FROM Orders o
JOIN Books b ON o.Book_ID = b.Book_ID
GROUP BY o.Book_ID, b.Title
ORDER BY Order_Count DESC
LIMIT 1;
```

---

## 🚀 How to Run

Clone the repository:
```bash
git clone https://github.com/yourusername/Online-Bookstore-SQL-Database.git
cd Online-Bookstore-SQL-Database
```

Open PostgreSQL and create the database:
```sql
CREATE DATABASE OnlineBookstore;
\c OnlineBookstore;
```

Run the SQL script (`bookstore.sql`) to create tables and import data.

Explore the queries inside `queries.sql` for insights.

---

## 📈 Insights from Advanced Queries
- Total revenue generated from orders  
- Top 3 most expensive Fantasy books  
- Customers with at least 2 orders  
- Remaining stock after fulfilling all orders  
- Cities with customers who spent more than $30  

---

## 🛠️ Tech Stack
- **Database:** PostgreSQL  
- **Data Import:** CSV files  
- **Queries:** SQL (DDL, DML, Joins, Aggregations)  

---

## 📄 License
This project is for **educational purposes** only. Feel free to use and modify.

---

👨‍💻 **Author:** Suraj Mateti  
🔗 GitHub: [yourusername](https://github.com/yourusername)
