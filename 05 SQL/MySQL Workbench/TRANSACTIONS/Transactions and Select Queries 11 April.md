### **Inventory Management System for a Warehouse**

You are tasked with designing a simple database for a warehouse that tracks products, employees, and shipments. The warehouse has different products, employees who handle these products, and the shipments of products to customers. You need to create a database that stores information about these entities.

### Requirements:
1. **Create a Database:**
   - Name: `WarehouseDB`

2. **Create 3 Tables:**
   - `Product` table (tracks products available in the warehouse)
     - `ProductID` (INT, primary key, auto-increment)
     - `ProductName` (VARCHAR)
     - `Category` (VARCHAR)
     - `QuantityInStock` (INT)
     - `Price` (DECIMAL)
   
   - `Employee` table (tracks warehouse employees)
     - `EmployeeID` (INT, primary key, auto-increment)
     - `FirstName` (VARCHAR)
     - `LastName` (VARCHAR)
     - `HireDate` (DATE)
     - `Position` (VARCHAR)
   
   - `Shipment` table (tracks the shipment of products to customers)
     - `ShipmentID` (INT, primary key, auto-increment)
     - `ProductID` (INT, foreign key referencing `Product(ProductID)`)
     - `EmployeeID` (INT, foreign key referencing `Employee(EmployeeID)`)
     - `ShipmentDate` (DATE)
     - `QuantityShipped` (INT)

3. **Insert at least 5 values in each table.**

4. **Create the following queries to retrieve specific data:**
   1. Retrieve all products that have a quantity greater than 50 in stock.
   2. Retrieve a list of employees hired after '2020-01-01'.
   3. Retrieve all shipments that were made by employee with `EmployeeID = 3`.
   4. Retrieve the name of the product and the employee who shipped it, including the shipment date.
     
   6. (Challenge) Retrieve the total quantity of each product that has been shipped.

5. **Create a transaction that updates a 'laptops''s price and deletes any shipment record.**

