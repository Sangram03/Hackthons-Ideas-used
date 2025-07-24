## 🔐 **What is this?**

This is an **Express middleware function** that:

* Validates a **JWT token** (JSON Web Token)
* Extracts the user's ID from it
* Attaches it to the request (`req.userId`)
* Blocks the request if the token is missing or invalid

---

```
import jwt from "jsonwebtoken";

const authMiddleware = async (req, res, next) => {
  const { token } = req.headers;

  if (!token) {
    return res.status(401).json({ success: false, message: "Not Authorized. Login Again." });
  }

  try {
    // ✅ THIS LINE MUST EXIST — this fixes "decoded is not defined"
    const decoded = jwt.verify(token, process.env.JWT_SECRET);

    // ✅ Save the user ID into req.userId so you can access it later
    req.userId = decoded.id;

    next();
  } catch (error) {
    console.error("JWT Error:", error.message);
    res.status(401).json({ success: false, message: "Invalid Token" });
  }
};

export default authMiddleware;


```

## 🧩 **Code Breakdown**

```js
import jwt from "jsonwebtoken";
```

* **jwt**: A library used to **verify**, **sign**, and **decode** JWT tokens.
* You're likely using `jsonwebtoken` from npm.

---

### 📦 Middleware Function

```js
const authMiddleware = async (req, res, next) => {
```

* This is an **Express middleware**.
* `req`, `res`, and `next` are standard arguments:

  * `req`: incoming request
  * `res`: response to send back
  * `next`: function to call the **next middleware** in the chain (if the token is valid)

---

### 1️⃣ **Check for Token**

```js
const { token } = req.headers;
```

* Assumes that the client sends the JWT token in the `headers`:

  ```http
  token: <your_jwt_token>
  ```

```js
if (!token) {
  return res.status(401).json({ success: false, message: "Not Authorized. Login Again." });
}
```

* If token is **missing**, respond with **401 Unauthorized**.

---

### 2️⃣ **Verify Token**

```js
const decoded = jwt.verify(token, process.env.JWT_SECRET);
```

* Validates the token using the **secret key** (`process.env.JWT_SECRET`)
* If valid, `decoded` will be the payload, e.g.:

  ```json
  {
    "id": "user123",
    "iat": 1723561726,
    "exp": 1723565326
  }
  ```

> If invalid (expired, forged), this throws an error → caught in `catch`.

---

### 3️⃣ **Attach Decoded Info to Request**

```js
req.userId = decoded.id;
```

* Saves the **user ID** in `req.userId`
* You can now access `req.userId` in any route that uses this middleware

---

### 4️⃣ **Call next()**

```js
next();
```

* If everything is valid, move on to the next middleware or route handler

---

### 5️⃣ **Catch Errors**

```js
} catch (error) {
  console.error("JWT Error:", error.message);
  res.status(401).json({ success: false, message: "Invalid Token" });
}
```

* If token is invalid or expired, return a **401 Unauthorized** error.

---

## ✅ Example Usage

### 👇 Applying the middleware to a route

```js
import express from "express";
import authMiddleware from "./authMiddleware.js";

const router = express.Router();

router.get("/profile", authMiddleware, async (req, res) => {
  const userId = req.userId;  // <-- this was set by the middleware
  // fetch user profile from DB using userId
  res.json({ message: `Welcome user ${userId}` });
});
```

---

## 🧪 Example Header Sent by Frontend

```http
token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

---

## 🌐 Where does the token come from?

Usually issued during **login/signup**:

```js
const token = jwt.sign({ id: user._id }, process.env.JWT_SECRET, { expiresIn: "1h" });
```

---

## 🛡️ Summary

| Step          | Purpose                            |
| ------------- | ---------------------------------- |
| Check token   | Ensures user is authenticated      |
| Verify token  | Ensures token hasn't been tampered |
| Extract ID    | So you can query DB by user ID     |
| Block or Pass | Blocks invalid users, passes valid |

---

