## 🧩 What is `try...catch`?

The `try...catch` statement lets you **test a block of code (try)** for errors, and **handle errors (catch)** if any occur — without breaking your entire program.

---

## ✅ Basic Syntax:

```js
try {
  // Code that might throw an error
} catch (error) {
  // Code to handle the error
}
```

---

## 🔍 How It Works:

* **`try` block:**
  The code here runs **normally**, unless an error occurs.

* **If an error happens**, JS **immediately stops** running the rest of the `try` block and jumps to the `catch` block.

* **`catch` block:**
  It **receives the error object** (often named `err` or `error`) and lets you **respond to or log the error**.

---

### 🧪 Example 1: Catching an Error

```js
try {
  const result = someUndefinedFunction(); // 🚨 ReferenceError
  console.log("This won't run");
} catch (error) {
  console.log("Caught an error:", error.message);
}
```

**Output:**

```
Caught an error: someUndefinedFunction is not defined
```

---

### 🧪 Example 2: No Error — `catch` not executed

```js
try {
  const x = 5 + 7;
  console.log(x);
} catch (err) {
  console.log("Will not run");
}
```

**Output:**

```
12
```

---

## 🛑 What kind of errors can `try...catch` handle?

It can only catch **runtime (synchronous) errors** like:

* `ReferenceError`, `TypeError`, `SyntaxError` (inside eval), etc.
* Code that throws manually using `throw`
* API call failures *if using async/await*

It **cannot** catch:

* Compile-time errors (e.g., wrong syntax outside `eval`)
* Asynchronous errors *unless awaited inside a try block*

---

## 🧱 Throwing Custom Errors

You can use `throw` inside `try` to throw custom errors:

```js
try {
  let age = -5;
  if (age < 0) {
    throw new Error("Age can't be negative");
  }
} catch (err) {
  console.log("Custom error:", err.message);
}
```

---

## ⚡ Optional: `finally` Block

You can add a `finally` block to run **code regardless of success or error**:

```js
try {
  console.log("Trying...");
  throw new Error("Oops");
} catch (err) {
  console.log("Caught:", err.message);
} finally {
  console.log("Always runs");
}
```

**Output:**

```
Trying...
Caught: Oops
Always runs
```

---

## ⚙️ Use Case with `async/await`

```js
async function fetchUserData() {
  try {
    const res = await fetch("https://api.example.com/user");
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error("Failed to load data:", err.message);
  }
}
```

---

## 🔑 Summary Table

| Keyword   | Purpose                                             |
| --------- | --------------------------------------------------- |
| `try`     | Wrap code that might throw an error                 |
| `catch`   | Handle the error (gets an `Error` object)           |
| `finally` | Optional — runs code regardless of success or error |
| `throw`   | Manually throw an error                             |

---

## 👨‍💻 Real Use Cases

* API request error handling
* Preventing app crash on unexpected user input
* Graceful file upload failure
* Fallback UI when something breaks

---

