# ELEVATE_LAB-TASK6
# 📊 Sales Trend Analysis Using SQL Aggregations

## 🧠 Project Summary

This project focuses on analyzing time-based trends in sales data using SQL. The goal is to derive **monthly insights on revenue and order volume** by aggregating and grouping data. The analysis is done on a structured dataset using **SQLite**, leveraging functions like `strftime()`, `SUM()`, and `COUNT()`.

---

## 🎯 Objectives

- Perform monthly aggregation of revenue and order volume.
- Group and summarize data based on time periods (year/month).
- Learn SQL techniques for handling time-series data.
- Practice basic database creation and CSV imports in SQLite.

---

## 📁 Dataset Description

The dataset used is `sample_orders.csv`, which contains eCommerce sales data. Each row represents a customer order.

### 📌 Table Name: `orders`

| Column Name | Data Type | Description                        |
|-------------|------------|------------------------------------|
| order_id    | INTEGER    | Unique identifier for each order   |
| order_date  | TEXT       | Date when the order was placed     |
| amount      | REAL       | Total amount (revenue) per order   |
| product_id  | INTEGER    | ID of the purchased product        |

> **Note**: The `order_date` is in the format `YYYY-MM-DD` to ensure compatibility with SQLite's `strftime()` function.

---

## 🛠️ Tools & Technologies Used

- **Database**: SQLite (via DB Browser for SQLite)
- **Language**: SQL
- **Data Source**: CSV file (manually imported)
- **IDE/Environment**: SQLite DB Browser, Visual Studio Code

---

## 🚀 Project Workflow

### 1. Create the Table in SQLite

```sql
CREATE TABLE orders (
  order_id INTEGER PRIMARY KEY,
  order_date TEXT,
  amount REAL,
  product_id INTEGER
);
SELECT 
  strftime('%Y', order_date) AS order_year,
  strftime('%m', order_date) AS order_month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM 
  orders
GROUP BY 
  order_year, order_month
ORDER BY 
  order_year, order_month;
📊 Sample Output
order_year	order_month	total_revenue	total_orders
2023	01	455.44	3
2023	02	465.00	2
2023	03	319.99	2
2023	04	549.48	3

🧠 Key SQL Concepts Applied
strftime('%Y', order_date): Extracts the year.

strftime('%m', order_date): Extracts the month.

SUM(amount): Calculates total revenue per group.

COUNT(DISTINCT order_id): Counts total unique orders.

GROUP BY: Groups data for monthly aggregation.

ORDER BY: Sorts the output by year and month.

📁 Project Structure
graphql
Copy
Edit
sales-trend-analysis-sql/
│
├── sample_orders.csv          # Sample dataset
├── sales_analysis.sql         # SQL script with query
└── README.md                  # Project documentation
📈 Learnings and Outcomes
Gained hands-on experience with SQL aggregation functions.

Learned how to extract month and year from dates using SQLite.

Built a foundational understanding of time-series data analysis in SQL.

Created a reusable template for sales trend reporting.

🔖 Possible Extensions
Add product-level trend analysis.

Visualize results using Power BI or Tableau.

Connect SQLite to Python for dashboarding.

👩‍💻 Author
Dharshini
🎓 B.E. Computer Science and Engineering
📌 Data analysis Intern
📧 dharshinisubramani3015@gmail.com










