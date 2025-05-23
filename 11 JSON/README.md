# 🤖**JSON**

### 📦 What is JSON?

**JSON** (JavaScript Object Notation) is:

> *"A lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate."* 📄🤖

✅ Used to store and exchange data
✅ Super readable and easy to work with
✅ Common in NoSQL databases like MongoDB 🛢️

---

### 🧱 JSON Building Blocks

#### 🔑 Key-Value Pairs

JSON stores data as pairs:

```json
{
  "name": "Bob",
  "age": 25
}
```

🗝️ `"name"` is the key
📦 `"Bob"` is the value

---

#### 🪆 Nested Objects

You can nest one object inside another:

```json
{
  "name": "Bob",
  "degree": {
    "name": "BSc IT",
    "year": 3
  }
}
```

📚 Useful for representing structured data like profiles or products.

---

#### 📚 Arrays of Objects

A list of items:

```json
[
  {
    "name": "Bob"
  },
  {
    "name": "Alice"
  }
]
```

🧑‍🤝‍🧑 Good for lists of users, products, events, etc.

---

### 💡 Why Use JSON?

🌐 **Web-friendly** – works great with APIs and JavaScript
🪶 **Lightweight** – smaller than XML
📊 **Flexible** – good for both structured and semi-structured data
🔥 **Default format in MongoDB** – no schema needed!

---

### 🛠️ MongoDB Example

Here’s how a race might be stored in MongoDB using JSON:

```json
{
  "name": "China 2019",
  "date": "2019-04-14",
  "racetrack": "Shanghai International Circuit"
}
```

🚀 You can insert this straight into a MongoDB collection!

---

## **JSON Code**🧪🔧

---

### 🧍 1. **User Profile**

```json
{
  "name": "Emma",
  "age": 27,
  "email": "Emma@example.com",
  "subscribed": true
}
```

🔍 Try changing `"subscribed"` to `false`, or add a `"phone"` key!

---

### 📦 2. **Product List**

```json
[
  {
    "id": 101,
    "name": "Gaming Laptop",
    "price": 18999.99,
    "inStock": true
  },
  {
    "id": 102,
    "name": "Mechanical Keyboard",
    "price": 1249.50,
    "inStock": false
  }
]
```

📚 Great to test arrays of objects — add another product or rename one!

---

### 🎬 3. **Movie Details**

```json
{
  "title": "Inception",
  "year": 2010,
  "genres": ["Action", "Sci-Fi", "Thriller"],
  "ratings": {
    "IMDb": 8.8,
    "RottenTomatoes": "87%"
  }
}
```

🛠️ Try adding a new rating source or genre!

---

### 🌍 4. **Nested Location Info**

```json
{
  "location": {
    "country": "South Africa",
    "city": "Durban",
    "coordinates": {
      "latitude": -29.8587,
      "longitude": 31.0218
    }
  }
}
```

🧭 Nesting levels make this fun to explore in tree view!

---

### 🧑‍🤝‍🧑 5. **Classroom of Students**

```json
{
  "className": "INSY6112",
  "students": [
    {"name": "Zanele", "marks": 78},
    {"name": "Liam", "marks": 65},
    {"name": "Kai", "marks": 90}
  ]
}
```

📊 You can try adding a new student or rename the class!

---


