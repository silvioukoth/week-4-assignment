# SQL Assignment: Aggregate Functions and Grouping

## 📌 Overview

This assignment focuses on using SQL aggregate functions and grouping operations to analyze data in a MySQL database. It uses the `payments`, `customers`, and `orderdetails` tables from the Classic Models database.

The assignment demonstrates how to calculate totals, averages, and maximum values, as well as how to sort and limit query results.

## 🎯 Objectives

- Use aggregate functions to summarize data.
- Apply the `GROUP BY` clause to group records.
- Sort query results using `ORDER BY`.
- Limit the number of returned records using `LIMIT`.
- Perform calculations using values from multiple columns.

## 🛠️ Tools and Technologies

- **Database:** MySQL
- **Database environment:** MySQL Workbench
- **Language:** SQL
- **Dataset:** Classic Models Database

## 📝 Assignment Questions and Solutions

### Question 1: Total Payment Amount for Each Payment Date

**Objective:** Calculate the total payment amount for each payment date, display the five latest dates, and sort them in descending order.

```sql
SELECT
    paymentDate,
    SUM(amount) AS total_amount
FROM payments
GROUP BY paymentDate
ORDER BY paymentDate DESC
LIMIT 5;
```

**Concepts used:** `SUM()`, `GROUP BY`, `ORDER BY`, and `LIMIT`.

### Question 2: Average Credit Limit of Each Customer

**Objective:** Display each customer's name, country, and average credit limit.

```sql
SELECT
    customerName,
    country,
    AVG(creditLimit) AS average_credit_limit
FROM customers
GROUP BY customerName, country;
```

**Concepts used:** `AVG()` and `GROUP BY`.

### Question 3: Total Price of Products Ordered

**Objective:** Calculate the total price for each product code and quantity ordered.

```sql
SELECT
    productCode,
    quantityOrdered,
    SUM(quantityOrdered * priceEach) AS total_price
FROM orderdetails
GROUP BY productCode, quantityOrdered;
```

**Concepts used:** `SUM()`, arithmetic operations, and `GROUP BY`.

### Question 4: Highest Payment Amount for Each Check Number

**Objective:** Find the highest payment amount associated with each check number.

```sql
SELECT
    checkNumber,
    MAX(amount) AS highest_amount
FROM payments
GROUP BY checkNumber;
```

**Concepts used:** `MAX()` and `GROUP BY`.

## 📚 Key SQL Concepts Learned

| SQL concept | Description |
|---|---|
| `SUM()` | Calculates the sum of values. |
| `AVG()` | Calculates the average of values. |
| `MAX()` | Returns the maximum value. |
| `GROUP BY` | Groups rows with matching values. |
| `ORDER BY` | Sorts query results. |
| `DESC` | Sorts results in descending order. |
| `LIMIT` | Restricts the number of rows returned. |
| Arithmetic operations | Calculate values using expressions such as `quantityOrdered * priceEach`. |

## ▶️ How to Run the Queries

1. Install and open MySQL Workbench.
2. Connect to your MySQL server.
3. Select the Classic Models database:

   ```sql
   USE classicmodels;
   ```

4. Open a new SQL query tab.
5. Copy and execute each query separately.
6. Review the result grid to verify the returned columns and values.

## 📂 Project Structure

```text
sql-assignment/
├── README.md
└── assignment.sql
```

The `README.md` file documents the assignment, while `assignment.sql` contains the four SQL queries.

## ✅ Conclusion

This assignment provides practical experience with SQL aggregate functions and data grouping. It strengthens the ability to summarize payment records, analyze customer credit limits, calculate product order totals, and identify the highest payment for each check number.

These skills are useful for database management, reporting, and data analysis.

---

**Author:** Silvio Ukoth Ukoro  
**Course/Module:** SQL and Database Fundamentals  
**Database:** MySQL Classic Models
