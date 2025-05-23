### 🔄 **1. Indexes**

**Purpose**:
Speed up data retrieval from large tables.

**What it is**:
A database structure that helps the database engine **quickly locate rows** without scanning the whole table.

**Key Points**:

* Improves performance of `SELECT`, `WHERE`, `JOIN`, and `ORDER BY`.
* Does **not store data**.
* Can be created on one or more columns.

**Example**:

```sql
CREATE INDEX idx_name ON customers(name);
```

---

### 👁️ **2. Views**

**Purpose**:
Provide a **virtual table** based on the result of a query.

**What it is**:
A saved `SELECT` query that behaves like a table but doesn't store data physically.

**Key Points**:

* Simplifies complex queries.
* Can restrict access to specific columns.
* Automatically reflects changes from underlying tables.

**Example**:

```sql
CREATE VIEW high_value_orders AS
SELECT * FROM orders WHERE total > 1000;
```

---

### ⚙️ **3. Stored Procedures**

**Purpose**:
Automate and encapsulate **a block of SQL statements** for reuse.

**What it is**:
A named routine that can accept parameters, perform operations, and return results.

**Key Points**:

* Can contain logic (IF, LOOP, etc.).
* Reusable and secure.
* Can include `IN`, `OUT`, and `INOUT` parameters.

**Example**:

```sql
CREATE PROCEDURE get_customer(IN custId INT)
BEGIN
  SELECT * FROM customers WHERE customer_id = custId;
END;
```

---

### 🧾 **4. Temporary Tables**

**Purpose**:
Store intermediate or session-specific data **temporarily**.

**What it is**:
A table that exists **only for the duration of a session** or until explicitly dropped.

**Key Points**:

* Used in complex operations or multi-step queries.
* Automatically deleted when the session ends.
* Can be created manually or from a query.

**Example**:

```sql
CREATE TEMPORARY TABLE recent_sales AS
SELECT * FROM sales WHERE sale_date >= '2025-01-01';
```

---

### 🔍 Table 

| Feature        | Stores Data  | Persistent | Used For                            | Example Use Case                  |
| -------------- | ------------ | ---------- | ----------------------------------- | --------------------------------- |
| **Index**      | No           | Yes        | Speeding up queries                 | Searching by customer name fast   |
| **View**       | No (virtual) | Yes        | Simplifying complex queries         | Viewing top customers             |
| **Procedure**  | No           | Yes        | Reusable SQL logic (actions)        | Inserting a new order             |
| **Temp Table** | Yes          | No         | Temporary data storage in a session | Holding intermediate join results |

---

![ChatGPT Image May 23, 2025, 01_45_43 PM](https://github.com/user-attachments/assets/f4e30b98-61ef-4a98-932e-5e78b37b5110)

