# task7
# Task 7 - Basic Sales Summary using SQLite and Python

## 📄 Objective

The goal of this project is to **generate a basic sales summary** by using SQL inside Python to query a SQLite database. The summary includes:
- Total quantity sold per product.
- Total revenue generated per product.
- Display the results using basic print statements and a simple bar chart.

---

## 🛠 Tools Used

- **Python** (with `sqlite3`, `pandas`, `matplotlib`)
- **SQLite** (built into Python)
- **Jupyter Notebook** or **Python script (.py file)**

---

## 📊 Dataset

A **small SQLite database** (`sales_data.db`) is created with one table: `sales`.

### Table structure:
- **id**: Auto-incremented primary key
- **product**: Name of the product sold (TEXT)
- **quantity**: Number of units sold (INTEGER)
- **price**: Price per unit (REAL)

Sample data includes sales records for products like Apple, Banana, Orange, etc.

---

## 🔍 What the Code Does

1. **Creates a SQLite Database** (`sales_data.db`) and a `sales` table if it doesn’t exist.
2. **Inserts Sample Sales Data** into the `sales` table.
3. **Executes SQL Queries** to summarize sales:
   - Groups sales by product.
   - Calculates total quantity sold and total revenue (`quantity * price`).
4. **Displays the Summary** as a printed DataFrame.
5. **Plots a Bar Chart** of revenue by product and saves it as `sales_chart.png`.

---

## 💡 SQL Query Used

```sql
SELECT 
    product, 
    SUM(quantity) AS total_qty, 
    SUM(quantity * price) AS revenue 
FROM sales 
GROUP BY product;
Sales Summary:
##output

  product  total_qty  revenue
0   Apple         15     37.5
1  Banana         25     30.0
2   Mango         12     33.6
3  Orange          7     21.0
