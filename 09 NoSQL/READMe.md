# **MongoDB**

## ✅ 1. **Understand What MongoDB Is**

MongoDB is:

* A **NoSQL** database.
* It stores data in **JSON-like documents** (called BSON).
* It’s schema-flexible — you don’t need to define the structure of your data upfront.

Think of it as:

```json
{
  "name": "Talia",
  "role": "Admin",
  "skills": ["Kotlin", "SQL", "Android"]
}
```

instead of rows and columns like SQL.

---

## ✅ 2. **Basic MongoDB Concepts**

| SQL Term | MongoDB Term |
| -------- | ------------ |
| Database | Database     |
| Table    | Collection   |
| Row      | Document     |
| Column   | Field        |

---

## ✅ 3. **Use `mongosh` to Interact with the Database**

Open `mongosh` and try:

```javascript
// Switch to a new or existing database
use myFirstDB

// Create a collection and insert a document
db.books.insertOne({ title: "The Alchemist", author: "Paulo Coelho", year: 1988 })

// View the document
db.books.find()

// Insert more data
db.books.insertMany([
  { title: "1984", author: "George Orwell", year: 1949 },
  { title: "Brave New World", author: "Aldous Huxley", year: 1932 }
])

// Query with a filter
db.books.find({ author: "George Orwell" })

// Count documents
db.books.countDocuments()
```

---

## ✅ 4. **Learn CRUD Operations**

**C**reate:

```javascript
db.users.insertOne({ name: "Alice" })
```

**R**ead:

```javascript
db.users.find()
```

**U**pdate:

```javascript
db.users.updateOne({ name: "Alice" }, { $set: { name: "Alicia" } })
```

**D**elete:

```javascript
db.users.deleteOne({ name: "Alicia" })
```

---

## ✅ 5. Optional GUI: Use MongoDB Compass (Visual Tool)

If you prefer **clicking over typing**, download **MongoDB Compass**:

* [https://www.mongodb.com/try/download/compass](https://www.mongodb.com/try/download/compass)

It lets you:

* View and edit databases visually
* Build queries with a UI
* Analyze data structures easily

---


