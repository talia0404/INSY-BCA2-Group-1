# 📋 `SELECT` Queries

A basic `SELECT` query looks like this:

```sql
SELECT column1, column2, ...
FROM table_name;
```

Here’s what each part means:
- **🔍 `SELECT`**: Specifies the **columns** you want to fetch.
- **📝 `column1, column2, ...`**: These are the columns you want from the table. You can use `*` to fetch **all columns**.
- **🏠 `FROM`**: Specifies the **table** where you want to retrieve data.
- **📂 `table_name`**: This is the **name** of the table from which you want to retrieve the data.

### 💡 Examples of `SELECT` Queries

#### 1. **Select All Columns from a Table**
To retrieve **all columns** from a table, use the wildcard `*`:

```sql
SELECT * FROM Customers;
```
- This will fetch **all columns** for **all rows** from the `Customers` table. It’s like saying “I want everything!” 🙌

#### 2. **Select Specific Columns**
You can specify which **columns** you want to retrieve:

```sql
SELECT FirstName, LastName FROM Customers;
```
- This will only return the `FirstName` and `LastName` columns from the `Customers` table. 🧑‍💼👩‍💼

#### 3. **Filtering Data with `WHERE`**
You can use the `WHERE` clause to filter data based on a condition:

```sql
SELECT * FROM Customers WHERE Age > 30;
```
- This will return **all columns** for customers who are older than 30 years. 🎂📊

#### 4. **Sorting Data with `ORDER BY`**
You can sort the data in ascending (`ASC`) or descending (`DESC`) order:

```sql
SELECT * FROM Customers ORDER BY LastName DESC;
```
- This will return all rows, sorted by `LastName` in descending order. 📑⬇️

#### 5. **Limiting Results with `LIMIT`**
You can use `LIMIT` to restrict how many rows to return:

```sql
SELECT * FROM Customers LIMIT 5;
```
- This will return the **first 5 rows** from the `Customers` table. ⏳

#### 6. **Using Aggregates (SUM, COUNT, AVG, etc.)**
You can use **aggregate functions** to get summary information:

```sql
SELECT COUNT(*) AS TotalCustomers FROM Customers;
```
- This will return the **total number of customers**. 🧮

```sql
SELECT AVG(Age) AS AverageAge FROM Customers;
```
- This will give the **average age** of all customers. 🎯

---

# 🔍**ORDER BY and GROUP BY**

The **
`ORDER BY`** and **`GROUP BY`** clauses are both used to organise and manipulate data in SQL queries, but they serve **different purposes** and work in distinct ways.

### 1. **`ORDER BY`** 🔢

The **`ORDER BY`** clause is used to **sort the result set** of a query in either **ascending** (`ASC`) or **descending** (`DESC`) order based on one or more columns. It **does not** group or aggregate data; instead, it simply sorts the results returned by the query. You use `ORDER BY` when you want the **data to be displayed in a specific order**, such as sorting names alphabetically, prices from low to high, or dates from newest to oldest.

#### **Syntax**:
```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 [ASC|DESC], column2 [ASC|DESC];
```

### 2. **`GROUP BY`** 🧮

The **`GROUP BY`** clause is used to **group rows** that have the same values in specified columns into summary rows. It is often used with **aggregate functions** (like `COUNT()`, `SUM()`, `AVG()`, etc.) to perform operations on each group of data. It groups the data based on column(s) and allows you to perform **aggregation** (like summing, counting, averaging) on each group. You use `GROUP BY` when you need to **aggregate data** or when you need to group rows into categories based on a common value.

- **First**, the `GROUP BY` clause groups the sales by `ProductName`, and for each product, it calculates the total sales using `SUM()`.
- **Then**, the `ORDER BY` clause sorts the result by the `TotalSales` column in **descending** order.
  
---

# **Joining Tables**

## 1. **INNER JOIN** 🔍

An **`INNER JOIN`** only returns rows where there is **a match** between the two tables. If there is no match in one of the tables, that row is excluded from the result.

**Example:**

Let’s assume we have the following tables:

**Employees Table:**
| EmployeeID | Name      |
|------------|-----------|
| 1          | John      |
| 2          | Alice     |
| 3          | Bob       |

**Departments Table:**
| DepartmentID | EmployeeID | DepartmentName |
|--------------|------------|----------------|
| 101          | 1          | HR             |
| 102          | 2          | Marketing      |


Here’s the query for an `INNER JOIN`:

```sql
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
INNER JOIN Departments ON Employees.EmployeeID = Departments.EmployeeID;
```

**Result:**
| Name  | DepartmentName |
|-------|----------------|
| John  | HR             |
| Alice | Marketing      |

---

## 2. **LEFT JOIN (or LEFT OUTER JOIN)** 🌿

A **`LEFT JOIN`** returns **all rows** from the **left table**, and the matching rows from the **right table**. If there is no match, it will still include the row from the left table, but the columns from the right table will be filled with `NULL`.

**Example:**

```sql
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
LEFT JOIN Departments ON Employees.EmployeeID = Departments.EmployeeID;
```

**Result:**
| Name  | DepartmentName |
|-------|----------------|
| John  | HR             |
| Alice | Marketing      |
| Bob   | NULL           |

- **Explanation**: All employees are returned, even if they don't have a corresponding department. **Bob** appears in the result with a `NULL` for `DepartmentName` because there's no matching entry in the `Departments` table for him.

---
