# **What is a View?**

A **view** in MySQL is a **virtual table**.
It does **not store data physically**. Instead, it shows the result of a **predefined SQL query** every time you access it.

You can think of a view as a **"saved SELECT statement"**.

Example:

```sql
CREATE VIEW ElectronicsProducts AS
SELECT ProductName, Price
FROM Products
WHERE Category = 'Electronics';
```

Whenever you run:

```sql
SELECT * FROM ElectronicsProducts;
```

MySQL executes that query on the original `Products` table and shows the result.

---

## **Why Do We Use Views?**

### **1. Simplification**

* Views make complex queries easier to use.
* Example: Instead of writing long joins every time, create a view that joins your tables once.

👉 **You only query the view.**

---

### **2. Security and Access Control**

* You can hide sensitive columns or rows from users.
* Example: Allow someone to see product names and prices, but not stock levels or supplier info.

👉 **Limit what different users see without modifying the main tables.**

---

### **3. Data Abstraction**

* Users interact with views, not the raw data structure.
* If table structures change, you can update the view instead of all applications.

👉 **Views help separate how data is stored from how it is used.**

---

### **4. Reusability**

* Once a view exists, any query or app can use it like a normal table.

👉 **This reduces duplication of SQL logic.**

---

### **5. Readability and Maintainability**

* Views clean up your SQL code.
* You avoid repeating complex filters, joins, or calculations.

👉 **This makes code easier to manage and debug.**

---

### **6. Data Aggregation or Formatting**

* You can create views to calculate totals, averages, etc.

Example:

```sql
CREATE VIEW SalesSummary AS
SELECT ProductID, SUM(Quantity) AS TotalSold
FROM Orders
GROUP BY ProductID;
```

👉 **Useful for reporting and dashboards.**

---
