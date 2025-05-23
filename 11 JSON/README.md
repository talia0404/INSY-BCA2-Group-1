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

