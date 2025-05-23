# **Temporary Tables**

A **temporary table** is a special type of table in SQL that is created and used **only for a short duration**, typically **within the same session or database connection**. It is mainly used to store **intermediate results** or **temporary data** during complex queries, batch processing, or data manipulation.

### 🔹 Key Features of Temporary Tables:

1. **Short-lived**:

   * Automatically deleted when the session or connection is closed.
   * You can also manually delete it using `DROP TEMPORARY TABLE`.

2. **Data is stored**:

   * Unlike views (which are virtual), temporary tables **store actual data**.

3. **Creation Syntax**:

   ```sql
   CREATE TEMPORARY TABLE temp_table_name (
       column1 datatype,
       column2 datatype,
       ...
   );
   ```

4. **Storage Types**:

   * **In-Memory**: Faster for small datasets, but uses limited RAM.
   * **On-Disk**: Better for large datasets, supports indexing, uses disk space.

5. **Limitations**:

   * Cannot use **foreign key constraints**.
   * Only accessible within the current session.

6. **Usage in Queries**:

   * You can use them in joins, subqueries, or even base them on query results:

     ```sql
     CREATE TEMPORARY TABLE temp_sales AS
     SELECT * FROM Sales WHERE SaleDate = CURDATE();
     ```

### 🔸 Why Use a Temporary Table?

* To **simplify complex joins or subqueries**.
* To **improve performance** by storing intermediate results.
* To **manipulate data temporarily** without affecting the actual database tables.

---
## Manual Definitions

In SQL, **Manual Definition** of a **temporary table** means that you **explicitly define the table structure** — specifying each column, data type, constraints, and storage engine — before inserting data into it.

### 🧾 Example of Manual Definition:

```sql
CREATE TEMPORARY TABLE current_season_races (
    race_id INT AUTO_INCREMENT NOT NULL,
    racetrack_id INT NOT NULL,
    name VARCHAR(250) CHARACTER SET utf8mb4 NOT NULL,
    date DATE NOT NULL,
    PRIMARY KEY (race_id)
) ENGINE=MEMORY;
```

### 🔍 Explanation:

* **You define the columns**: `race_id`, `racetrack_id`, `name`, and `date`.
* **You set constraints** like `NOT NULL` and `PRIMARY KEY`.
* You can **control storage** with `ENGINE=MEMORY`, meaning the table exists only in RAM (faster but volatile).
* This allows **customization** that automatic creation from a query doesn’t allow — such as indexing, character sets, default values, and column order.

---

### 🆚 Comparison

| Method                | Description                                                                 |
| --------------------- | --------------------------------------------------------------------------- |
| **Manual Definition** | You write out the full table structure manually.                            |
| **From Query**        | The table is automatically created based on the result of a `SELECT` query. |

**From Query Example:**

```sql
CREATE TEMPORARY TABLE current_season_races AS
SELECT * FROM race WHERE date >= '2020-01-01';
```

This second version **copies structure and data**, but you **can't control things like types, keys, or engine**.


