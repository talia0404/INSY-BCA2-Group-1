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
