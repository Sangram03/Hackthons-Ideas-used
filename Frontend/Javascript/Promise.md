## 🔗 What is a Promise?

A **Promise** is a built-in **JavaScript object** that represents the **eventual result** (or failure) of an **asynchronous operation**.

Think of a Promise like ordering food:

* **Pending** → You placed the order.
* **Fulfilled** → You got your food.
* **Rejected** → The order failed.

---

## ✅ Syntax:

```javascript
const promise = new Promise((resolve, reject) => {
  // Do something async
  if (success) {
    resolve(result); // fulfilled
  } else {
    reject(error);   // rejected
  }
});
```

---

## 📌 States of a Promise:

| State       | Description                                    |
| ----------- | ---------------------------------------------- |
| `pending`   | Initial state, neither fulfilled nor rejected  |
| `fulfilled` | Operation completed successfully (`resolve()`) |
| `rejected`  | Operation failed (`reject()`)                  |

---

## ✅ Example 1: Creating a Promise

```javascript
const myPromise = new Promise((resolve, reject) => {
  const value = true;

  if (value) {
    resolve("Promise resolved!");
  } else {
    reject("Promise rejected.");
  }
});
```

---

## ✅ Example 2: Consuming a Promise with `.then()` and `.catch()`

```javascript
myPromise
  .then(result => {
    console.log(result); // "Promise resolved!"
  })
  .catch(error => {
    console.error(error); // "Promise rejected."
  });
```

---

## 🔄 `then()` and `catch()` chaining:

```javascript
fetch("https://api.example.com/data")
  .then(response => response.json()) // wait for JSON parsing
  .then(data => console.log(data))   // log the data
  .catch(error => console.error(error)); // handle error
```

---

## 🧪 Example 3: Simulating delay with `setTimeout`

```javascript
const delayedPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Done after 2 seconds");
  }, 2000);
});

delayedPromise.then(msg => console.log(msg));
```

---

## ✅ Example 4: Using `async/await` with Promises

```javascript
async function run() {
  try {
    const result = await delayedPromise;
    console.log(result);
  } catch (err) {
    console.error(err);
  }
}

run();
```

---

## 🔁 Running Promises in Parallel: `Promise.all()`

```javascript
const p1 = Promise.resolve("A");
const p2 = Promise.resolve("B");

Promise.all([p1, p2]).then(results => {
  console.log(results); // ["A", "B"]
});
```

---

## ⚠️ Common Mistakes:

### ❌ Forgetting `.catch()` (unhandled rejection):

```javascript
fetch("bad_url") // If error happens, and no .catch(), it crashes
```

### ✅ Always handle errors:

```javascript
fetch("bad_url")
  .then(res => res.json())
  .catch(err => console.error("Caught:", err));
```

---

## 📚 Real-Life Use Cases:

| Use Case     | Where You Use Promises              |
| ------------ | ----------------------------------- |
| API calls    | `fetch()`, `axios.get()`            |
| File reading | `fs.promises.readFile()` in Node.js |
| User actions | Waiting for input, form submissions |
| Time delay   | `setTimeout()` wrapped in a Promise |

---
