```js
const salt = await bcrypt.genSalt(10);
const hashedPassword = await bcrypt.hash(password, salt);
```

---

## 🔐 Goal

This code is used to **encrypt (hash) user passwords** before saving them into a database — so even if the database is compromised, the actual passwords are not exposed.

---

## 🔹 Step-by-Step Explanation

### ✅ 1. `const salt = await bcrypt.genSalt(10);`

* `bcrypt.genSalt(rounds)` generates a **cryptographic salt**.
* The argument `10` is the **cost factor** — it controls how many times the algorithm will run to make the hash **stronger** (but also slower).
* Higher number = more secure = slower.

📦 Example output:

```js
$2b$10$sdf5eEWtA5UY3xQGbWxa8O
```

> 🔹 Think of salt as a **random string added to the password** before hashing to prevent "rainbow table attacks" (precomputed hashes).

---

### ✅ 2. `const hashedPassword = await bcrypt.hash(password, salt);`

* Hashes the **user's plain password** using the **generated salt**.
* `bcrypt.hash(plainTextPassword, salt)` → produces a **one-way encrypted string**.

📦 Example output:

```js
$2b$10$sdf5eEWtA5UY3xQGbWxa8Oe6ZHkQ3M0fOm2R0s28WdTWyXnhj9bcK
```

* This **cannot be reversed** — even the developer can't retrieve the original password.

---

## 🔄 Why Use Salt?

If two users use the **same password**, the **salt ensures** their hashed passwords are **completely different**.

Without salt:

```js
bcrypt.hash("password123") ➝ same output for everyone
```

With salt:

```js
bcrypt.hash("password123", salt1) ➝ different
bcrypt.hash("password123", salt2) ➝ different
```

---

## 🔒 How to Compare Later

When a user logs in, you compare their input like this:

```js
const isMatch = await bcrypt.compare(inputPassword, storedHashedPassword);
```

If `inputPassword` matches the original one used to generate the hash, it will return `true`.

---

## 🧠 Summary Table

| Line                          | Meaning                                       |
| ----------------------------- | --------------------------------------------- |
| `bcrypt.genSalt(10)`          | Creates a random string (salt) with 10 rounds |
| `bcrypt.hash(password, salt)` | Hashes the password using the salt            |
| Output                        | A secure, one-way hashed string to save in DB |
| Compare                       | Use `bcrypt.compare()` during login           |

---

