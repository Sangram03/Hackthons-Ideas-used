### 🌿 What is `dotenv` in Node.js?

**`dotenv`** is a **zero-dependency Node.js module** that lets you **load environment variables** from a `.env` file into `process.env`. It helps keep **sensitive config data** (like API keys, passwords, DB URLs) **out of your source code**.

---

## 📦 Why use `dotenv`?

✅ Keeps your app secure
✅ Easy to configure and use
✅ Makes your code portable and environment-specific

---

## 🛠️ Step-by-Step Installation

### 1️⃣ Install the Package

```bash
npm install dotenv
```

---

### 2️⃣ Create a `.env` File in Your Project Root

Example:

```env
PORT=3000
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/mydb
JWT_SECRET=mySuperSecretKey
```

> **⚠️ Never commit your `.env` file to GitHub!**
> Add it to `.gitignore`:

```bash
echo ".env" >> .gitignore
```

---

### 3️⃣ Load `.env` in Your Project

At the **top of your `server.js` or `index.js` file**:

```js
require('dotenv').config();
```

Now you can access the values using `process.env`:

```js
const PORT = process.env.PORT;
const db = process.env.MONGO_URI;
const secret = process.env.JWT_SECRET;

console.log(PORT); // Output: 3000
```

---

## 🔐 Example with Express

```js
// server.js
require('dotenv').config();
const express = require('express');

const app = express();
const PORT = process.env.PORT || 4000;

app.get('/', (req, res) => {
  res.send('API Running!');
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

---

## 📄 .env Example (for MERN App)

```env
PORT=4000
MONGO_URI=mongodb://localhost:27017/myapp
JWT_SECRET=secret123
CLOUDINARY_API_KEY=abc123
```

---

## ✅ Benefits Recap

| Feature           | Benefit                           |
| ----------------- | --------------------------------- |
| Security          | Keeps secrets out of codebase     |
| Config Management | Easy env switching (dev, prod)    |
| Simplicity        | One line setup (`.config()`)      |
| Compatibility     | Works with Node.js, Express, etc. |

---

Would you like help setting up `.env` in a **MERN stack project** or **deploying with environment variables** on Vercel, Render, or Netlify?
