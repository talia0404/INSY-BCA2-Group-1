**SQL** stands for **Structured Query Language**. It's a standard language used to manage and interact with relational databases.

### **What SQL Is Used For**

1. **Creating databases and tables**
      
   ```sql
   CREATE DATABASE databasename
   
   CREATE TABLE students (
       id INT,
       name VARCHAR(100),
       age INT
   );
   ```

3. **Inserting data**
   
   ```sql
   INSERT INTO students (id, name, age)
   VALUES (1, 'Sarah', 22);
   ```

4. **Querying data**
   
   ```sql
   SELECT name, age FROM students WHERE age > 20;
   ```

6. **Updating data**
   
   ```sql
   UPDATE students SET age = 23 WHERE id = 1;
   ```

8. **Deleting data**

   ```sql
   DELETE FROM students WHERE id = 1;
   ```

9. **Managing user access and security**
   - Grant or revoke permissions for users

---

### **Why SQL Matters**

- It’s used by almost **every major relational database** (MySQL, PostgreSQL, Oracle, SQL Server, SQLite, etc.).
- It helps you **store, organise, and analyse data** efficiently.
- SQL is essential in many fields: software development, data analysis, data engineering, and more.

