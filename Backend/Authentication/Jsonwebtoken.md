## 🔐 What is a JWT?

A **JWT** is a **compact, URL-safe token** that contains **encoded JSON data**. It's typically used to verify a user’s identity after they log in.

A token looks like this:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.
eyJ1c2VySWQiOiIxMjM0NTYiLCJyb2xlIjoiYWRtaW4ifQ.
Abc123XYZ987TOKEN_SIGNATURE
```

---

## 📦 Structure of a JWT

A JWT has **3 parts**, separated by dots (`.`):

1. **Header**:
   Describes the token type and hashing algorithm
   Example:

   ```json
   {
     "alg": "HS256",
     "typ": "JWT"
   }
   ```

2. **Payload**:
   The actual data or "claims" like user ID, role, etc.
   Example:

   ```json
   {
     "userId": "123456",
     "role": "admin",
     "exp": 1710000000
   }
   ```

3. **Signature**:
   Used to verify that the token wasn't changed.
   Created using:

   ```
   HMACSHA256(base64UrlEncode(header) + "." + base64UrlEncode(payload), secret)
   ```

---

## 🔐 Example Use Case: User Login

1. ✅ User logs in with username/password

2. 🖥️ Server verifies credentials

3. 🔏 Server creates a JWT and sends it back

4. 📲 Client stores the token (e.g., in localStorage)

5. 🔄 On every request, the client sends this token in headers:

   ```http
   Authorization: Bearer eyJhbGciOi...
   ```

6. 🛡️ Server verifies the token to allow/deny access

---

## ✅ Advantages

* Stateless: No need to store sessions on the server
* Compact: Easy to send in headers, cookies, etc.
* Self-contained: All needed data is inside the token

---

## ❗ Security Tips

* Always use **HTTPS** to prevent token theft
* Store tokens securely (e.g., **HTTP-only cookies** if possible)
* Use short **expiration times**
* Refresh tokens securely

---

## 🛠️ Libraries

In Node.js, common JWT libraries are:

```bash
npm install jsonwebtoken
```

Usage:

```js
const jwt = require('jsonwebtoken');

const token = jwt.sign({ userId: 123 }, 'mySecretKey', { expiresIn: '1h' });

const decoded = jwt.verify(token, 'mySecretKey');
```

---

Would you like a full example of JWT with **Node.js Express login system** or a **React frontend + backend token flow**?
