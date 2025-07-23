## 🛡️ What is CORS?

**CORS** stands for **Cross-Origin Resource Sharing**.

### 🔥 Problem it solves:

By default, browsers **block requests** made from a different origin (domain, port, or protocol). This is a **security feature**.

### ✅ CORS allows:

You to tell the browser:

> “Hey! This API (backend) is allowed to be called from that frontend (another domain).”

---

## 🔧 Installing the `cors` package

Before using `cors()`, you need to install it:

```bash
npm install cors
```

---

## ✅ Basic Usage

```js
import express from "express";
import cors from "cors";

const app = express();

app.use(cors()); // 👈 Enables CORS for all origins
```

This tells the browser:

> Allow any domain to send requests to this API.

---

## 🌍 Default Behavior of `cors()`

When you call `cors()` **without any arguments**, it allows:

* **All origins**
* All headers
* All methods (GET, POST, etc.)

This is fine for development but not recommended for production.

---

## 🛠️ Custom Configuration

To **restrict access**, you can pass options:

```js
app.use(cors({
  origin: "https://my-frontend.com", // allow only this domain
  methods: ["GET", "POST"],
  credentials: true, // if using cookies or auth headers
}));
```

---

## 🧪 Real-World Example

### Frontend (React on port 3000):

```js
axios.get("http://localhost:5000/api/data");
```

### Backend (Node/Express on port 5000):

```js
import express from "express";
import cors from "cors";

const app = express();
app.use(cors());

app.get("/api/data", (req, res) => {
  res.json({ message: "Hello from server" });
});
```

Without `cors()`, the browser would block the request. With it, the request succeeds.

---

## ⚠️ When to Use `cors()`

| Use Case                                               | Needed? |
| ------------------------------------------------------ | ------- |
| Frontend and backend on **same domain**                | ❌ No    |
| Frontend and backend on **different domains or ports** | ✅ Yes   |

---

## 🔚 Summary

| Term     | Meaning                                        |
| -------- | ---------------------------------------------- |
| `cors()` | Middleware to enable cross-origin requests     |
| Default  | Allows all origins (useful in dev)             |
| Custom   | You can restrict origins, methods, credentials |
| Use case | React frontend calling Node backend            |

---

