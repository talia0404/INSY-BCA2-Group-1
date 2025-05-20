# 🌟 **The Pixel Café Management System**

Welcome to **The Pixel Café**, the coolest tech-themed coffee shop in town. Customers love the quirky drink names, snack combinations, and the friendly staff.
You’ve been hired as the database manager to help organize operations using SQL.

---

### 🗄️ **Tables**

#### 1️⃣ `Drinks`

```sql
CREATE TABLE Drinks (
    DrinkID INT PRIMARY KEY AUTO_INCREMENT,
    DrinkName VARCHAR(100),
    Price DECIMAL(5,2),
    Type VARCHAR(50) -- e.g., Coffee, Tea, Smoothie, etc.
);

INSERT INTO Drinks (DrinkName, Price, Type) VALUES
('Byte Brew', 25.00, 'Coffee'),
('Java Jolt', 30.00, 'Coffee'),
('Pixel Punch', 28.00, 'Smoothie'),
('Syntax Sip', 24.00, 'Tea'),
('Bug Buster', 26.00, 'Coffee'),
('Code Cooler', 32.00, 'Smoothie'),
('Null Null Latte', 35.00, 'Coffee'),
('RAM Raspberry', 29.00, 'Smoothie'),
('Logic Lemonade', 20.00, 'Soft Drink'),
('Kernel Cappuccino', 33.00, 'Coffee'),
('Algorithm Americano', 27.00, 'Coffee'),
('CSS Chai', 23.00, 'Tea'),
('Overload Orange', 28.00, 'Smoothie'),
('Compile Cooler', 26.00, 'Soft Drink'),
('IP Infusion', 34.00, 'Smoothie'),
('Framework Frappé', 35.00, 'Coffee'),
('GPU Green Tea', 24.00, 'Tea'),
('Data Detox', 30.00, 'Smoothie'),
('Pixelated Punch', 22.00, 'Soft Drink'),
('Terminal Tonic', 21.00, 'Soft Drink');
```

#### 2️⃣ `Snacks`

```sql
CREATE TABLE Snacks (
    SnackID INT PRIMARY KEY AUTO_INCREMENT,
    SnackName VARCHAR(100),
    Price DECIMAL(5,2)
);

INSERT INTO Snacks (SnackName, Price) VALUES
('Binary Brownie', 15.00),
('Cookie Compiler', 18.00),
('Array Almond Bar', 12.00),
('Loop Lemon Tart', 16.00),
('Pointer Pretzel', 10.00),
('Bit Bites', 14.00),
('Function Fudge', 20.00),
('Stack Scone', 17.00),
('Queue Quiche', 25.00),
('Kernel Krispies', 13.00),
('Overclocked Oatmeal', 12.00),
('RAM Raisin Muffin', 19.00),
('Choco Chip Chipset', 15.00),
('Cache Croissant', 16.00),
('Bug-free Bagel', 13.00),
('Lambda Lemon Pie', 21.00),
('Protocol Popcorn', 10.00),
('Virtual Vanilla Slice', 22.00),
('Cloud Cookie', 18.00),
('Pixel Pecan Pie', 23.00);
```

#### 3️⃣ `Orders`

```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY AUTO_INCREMENT,
    DrinkID INT,
    SnackID INT,
    Quantity INT,
    OrderDate DATE,
    FOREIGN KEY (DrinkID) REFERENCES Drinks(DrinkID),
    FOREIGN KEY (SnackID) REFERENCES Snacks(SnackID)
);

-- Example: 20 random orders (for real use, randomize dates & IDs)
INSERT INTO Orders (DrinkID, SnackID, Quantity, OrderDate) VALUES
(1, 5, 2, '2025-05-01'),
(2, 4, 1, '2025-05-02'),
(3, 1, 1, '2025-05-03'),
(4, 3, 3, '2025-05-04'),
(5, 6, 2, '2025-05-05'),
(6, 8, 1, '2025-05-06'),
(7, 2, 2, '2025-05-07'),
(8, 9, 1, '2025-05-08'),
(9, 7, 2, '2025-05-09'),
(10, 11, 1, '2025-05-10'),
(11, 10, 2, '2025-05-11'),
(12, 12, 1, '2025-05-12'),
(13, 14, 3, '2025-05-13'),
(14, 15, 1, '2025-05-14'),
(15, 13, 2, '2025-05-15'),
(16, 16, 1, '2025-05-16'),
(17, 18, 2, '2025-05-17'),
(18, 17, 1, '2025-05-18'),
(19, 19, 1, '2025-05-19'),
(20, 20, 2, '2025-05-20');
```

---

### 🎯 **10 View Questions**


1. 
   Create a view that shows all drinks that are classified as 'Coffee'.


2. 
   Create a view that lists all snacks priced under R15.


3. 
   Create a view that shows the full order details (OrderID, DrinkName, SnackName, Quantity, OrderDate).
   (Hint: You will need joins)

4. 
   Create a view of all drinks and snacks combinations where both prices are above R25.

5. 
   Create a view that shows the total number of orders placed for each drink.

6. 
   Create a view that shows the most expensive drink and the most expensive snack in the café.

7. 
   Create a view that lists drinks which have never been ordered.

8. 
   Create a view that shows orders placed in May 2025 only.

9. 
   Create a view that shows orders where the combined price of the drink and snack is greater than R50.

10. 
    Create a view that shows the daily total revenue (sum of Drink Price + Snack Price multiplied by Quantity) for all orders.

---
