`bcryptjs` is a JavaScript library used to **securely hash and compare passwords** in Node.js applications.

---

### 🔐 Why Use `bcryptjs`?

When users sign up, you **should not store plain text passwords**. Instead, you hash the password using a secure algorithm so that:

* Even if your database is hacked, passwords remain unreadable.
* Passwords can be verified during login without ever exposing the original one.

---

### 🆚 `bcryptjs` vs `bcrypt`

| Library    | Written In | Native Dependency | Works Everywhere      | Speed           |
| ---------- | ---------- | ----------------- | --------------------- | --------------- |
| `bcrypt`   | C++ + JS   | Yes (node-gyp)    | No (harder to deploy) | Faster          |
| `bcryptjs` | Pure JS    | No                | Yes (very portable)   | Slightly slower |

**✅ Use `bcryptjs`** if you want maximum portability and easy installation (especially for serverless or frontend environments).

---

### ✅ Installation

```bash
npm install bcryptjs
```

---

### 🔧 Example Usage

```js
import bcrypt from 'bcryptjs';

// 1. Hashing a password
const plainPassword = 'mySecret123';
const hashedPassword = await bcrypt.hash(plainPassword, 10); // 10 = salt rounds
console.log('Hashed:', hashedPassword);

// 2. Comparing password on login
const isMatch = await bcrypt.compare('mySecret123', hashedPassword);
console.log('Do they match?', isMatch);
```

---

### 🧠 How It Works

* `bcrypt.hash(password, saltRounds)`: Encrypts the password using a salt.
* `bcrypt.compare(plain, hashed)`: Checks if a plain password matches the hashed one.

---

### 📌 Summary

| Feature          | Description                                        |
| ---------------- | -------------------------------------------------- |
| Hashing          | Converts password into a secure string             |
| Salting          | Adds randomness to prevent common password attacks |
| Comparison       | Checks if a login password matches the hash        |
| Use in Auth APIs | Common in login/registration backends              |

---
