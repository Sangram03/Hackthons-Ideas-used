### 🔐 What is `jsonwebtoken`?

`jsonwebtoken` (or **JWT**) is a **Node.js library** used to create, sign, verify, and decode **JSON Web Tokens**. These tokens are commonly used for **authentication** and **secure data exchange** between client and server.

---

## 📄 Official Documentation

**NPM Package**: [https://www.npmjs.com/package/jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
**GitHub**: [https://github.com/auth0/node-jsonwebtoken](https://github.com/auth0/node-jsonwebtoken)

---

## 📦 Installation

```bash
npm install jsonwebtoken
```

---

## 🧠 What is a JWT (JSON Web Token)?

A JWT is a **string** made up of **three parts** separated by dots (`.`):

```
header.payload.signature
```

Example:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.
eyJ1c2VySWQiOjEyMywidXNlcm5hbWUiOiJKb2huIn0.
3f5kL8hFv4NHaTf1qkqA19k9zWQ5KUhKXvU7Dycv6sA
```

---

## 🔧 Basic Usage

### 1. **Import the package**

```js
const jwt = require('jsonwebtoken');
```

---

### 2. **Create/Sign a Token**

```js
const token = jwt.sign(
  { userId: 123, username: 'john' },  // payload (data)
  'mySecretKey',                     // secret
  { expiresIn: '1h' }                // options
);

console.log(token);
```

---

### 3. **Verify a Token**

```js
jwt.verify(token, 'mySecretKey', (err, decoded) => {
  if (err) {
    console.log("Invalid token");
  } else {
    console.log("Decoded data:", decoded);
  }
});
```

---

### 4. **Decode a Token (without verifying)**

```js
const decoded = jwt.decode(token);
console.log(decoded);
```

> ⚠️ `.decode()` just decodes the payload, it does **not** check if the token is valid or tampered.

---

## 📁 Common JWT Usage in Express (Authentication Middleware)

```js
const express = require('express');
const jwt = require('jsonwebtoken');
const app = express();

const secret = 'mySecretKey';

function authMiddleware(req, res, next) {
  const token = req.headers.authorization?.split(" ")[1];
  if (!token) return res.status(401).send("Access Denied");

  jwt.verify(token, secret, (err, decoded) => {
    if (err) return res.status(403).send("Invalid Token");
    req.user = decoded;
    next();
  });
}

app.get('/protected', authMiddleware, (req, res) => {
  res.send(`Hello ${req.user.username}`);
});

app.listen(3000, () => console.log("Server running"));
```

---

## ⚙️ Common Options in `sign()`

| Option      | Description                            |
| ----------- | -------------------------------------- |
| `expiresIn` | Set token expiration (e.g. `1h`, `2d`) |
| `algorithm` | Signing algorithm (default: `HS256`)   |
| `issuer`    | Identifies the token's issuer          |
| `audience`  | Identifies the token's audience        |

---

## 🔐 Example Use Cases

* User authentication
* Stateless sessions
* API access control
* Password reset links

---

## 🧾 Summary

| Feature        | Description                      |
| -------------- | -------------------------------- |
| Library Name   | `jsonwebtoken`                   |
| Common Methods | `sign()`, `verify()`, `decode()` |
| Use Case       | Auth, secure data transfer       |
| Format         | Header.Payload.Signature         |

---

