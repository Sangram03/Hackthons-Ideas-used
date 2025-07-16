### 🔧 **1. Connecting to MongoDB Atlas**

After creating your cluster on [https://cloud.mongodb.com](https://cloud.mongodb.com), you'll get a connection string.

#### **Connection Command:**

```bash
mongosh "mongodb+srv://<username>:<password>@<cluster-url>/test"
```

Replace:

* `<username>` with your Atlas DB user
* `<password>` with the password you created
* `<cluster-url>` with your cluster's URL

---

### 📁 **2. Show All Databases**

```js
show dbs
```

---

### 📂 **3. Create or Switch to a Database**

```js
use myDatabase
```

---

### 📄 **4. Show All Collections (Tables)**

```js
show collections
```

---

### 🟢 **5. Insert Data into Collection**

```js
db.users.insertOne({ name: "Sangram", age: 23 })
```

Multiple documents:

```js
db.users.insertMany([
  { name: "Ram", age: 25 },
  { name: "Shyam", age: 30 }
])
```

---

### 🔍 **6. Read Data (Query)**

```js
db.users.find() // Show all
```

With filter:

```js
db.users.find({ age: { $gt: 25 } })
```

Pretty print:

```js
db.users.find().pretty()
```

---

### 📝 **7. Update Data**

Update one:

```js
db.users.updateOne(
  { name: "Ram" },
  { $set: { age: 26 } }
)
```

Update many:

```js
db.users.updateMany(
  { age: { $lt: 30 } },
  { $set: { status: "active" } }
)
```

---

### ❌ **8. Delete Data**

Delete one:

```js
db.users.deleteOne({ name: "Shyam" })
```

Delete many:

```js
db.users.deleteMany({ age: { $lt: 25 } })
```

---

### 🧾 **9. Drop Collection**

```js
db.users.drop()
```

---

### 💣 **10. Drop Database**

```js
db.dropDatabase()
```

---

### 📌 BONUS: MongoDB Atlas GUI Tools

* **MongoDB Compass** – GUI client for MongoDB.
* **MongoDB Atlas Web UI** – Browse your data right on the browser.

---

