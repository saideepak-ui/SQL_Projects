# SQL_Projects
# SQL-Based Data Analysis Project

This project involves in-depth data analysis using **Structured Query Language (SQL)** on two real-world datasets: **Employee Data** and **Automobile Sales Data**. The objective is to extract actionable business insights, apply SQL concepts for querying, and demonstrate strong proficiency in handling relational databases.

## 📌 Objective

- Perform exploratory data analysis using SQL.
- Gain insights into employee management and automotive industry trends.
- Demonstrate proficiency in SQL querying, aggregation, joins, subqueries, and window functions.
- Present business-level conclusions using SQL logic alone.

## 🗂️ Datasets

1. **Employee Dataset**
   - Fields: `emp_id`, `emp_name`, `department`, `salary`, `join_date`, `location`
2. **Automobile Sales Dataset**
   - Fields: `car_id`, `brand`, `model`, `price`, `region`, `sale_date`

*Note: Data is either mock-generated or based on publicly available samples.*

## 🛠️ Tools Used

- **MySQL** and **SQLite** for query execution.
- **DB Browser for SQLite** for offline querying.
- **VS Code** for writing and maintaining SQL scripts.

## 🚀 Project Highlights

### 🔹 Data Cleaning
- Handled missing data using `COALESCE`, `IS NULL`, and conditional updates.
- Standardized inconsistent naming conventions using `LOWER()`, `UPPER()`, and `REPLACE()`.

### 🔹 Employee Analysis
- Top 5 highest-paid employees per department.
- Average salary per department and location.
- Employees who joined in a specific year/month.
- Department-wise salary expenditure.

### 🔹 Automobile Sales Analysis
- Most sold brands per region using `RANK()` and `PARTITION BY`.
- Monthly and yearly sales trends.
- High revenue-generating brands and pricing patterns.

### 🔹 Performance Optimization
- Used indexes and analyzed query execution plans.
- Applied subqueries, CTEs, and views to simplify complex queries.

## 🧠 Sample SQL Query

```sql
-- Top 3 selling car brands per region
SELECT region, brand, total_sales FROM (
  SELECT region, brand, SUM(price) AS total_sales,
         RANK() OVER (PARTITION BY region ORDER BY SUM(price) DESC) AS rank
  FROM automobile_sales
  GROUP BY region, brand
) AS ranked_sales
WHERE rank <= 3;
📊 Key Learnings
Advanced use of SQL joins, aggregate functions, and window functions.

Real-world experience in cleaning, transforming, and analyzing data.

Identifying anomalies, trends, and strategic insights through SQL queries.

📁 Folder Structure
pgsql
Copy
Edit
sql-based-analysis/
│
├── employee_analysis.sql
├── automobile_analysis.sql
├── README.md
└── sample_datasets/
    ├── employee_data.csv
    └── automobile_data.csv
👨‍💻 Author
Munja Saideepak
