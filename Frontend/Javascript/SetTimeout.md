## 🔹 What is `setTimeout`?

`setTimeout()` is a built-in JavaScript function that executes a **function or code** **once** **after a specified delay** (in milliseconds).

---

## 🧠 Syntax:

```javascript
setTimeout(function, delay, ...args);
```

| Parameter  | Description                                   |
| ---------- | --------------------------------------------- |
| `function` | The function to run                           |
| `delay`    | Time in **milliseconds** (1000 ms = 1 second) |
| `...args`  | Optional arguments passed to the function     |

---

## ✅ Example 1: Basic Usage

```javascript
setTimeout(() => {
  console.log("Hello after 2 seconds!");
}, 2000); // runs once after 2 seconds
```

---

## ✅ Example 2: Passing a Named Function

```javascript
function greet(name) {
  console.log("Hi " + name);
}

setTimeout(greet, 3000, "Sangram"); // Hi Sangram after 3 seconds
```

---

## ✅ Example 3: Canceling a Timeout

Use `clearTimeout()` to **cancel** a scheduled timeout.

```javascript
const id = setTimeout(() => {
  console.log("This will NOT run");
}, 5000);

clearTimeout(id); // cancels the timeout before it runs
```

---

## ✅ Example 4: Use Case — Delayed UI Action

```javascript
button.addEventListener("click", () => {
  showLoader();
  setTimeout(hideLoader, 2000); // hide after 2 seconds
});
```

---

## ⏱ Real-World Use Cases

| Use Case         | Example                           |
| ---------------- | --------------------------------- |
| Debouncing input | Delay action until typing stops   |
| Delayed UI       | Show/hide loaders or alerts       |
| Lazy loading     | Delay loading of images/scripts   |
| Simulate delay   | For animations, API retries, etc. |

---

## ⚠️ Important Notes:

1. `setTimeout` is **asynchronous** — it doesn't block the main thread.
2. Actual delay is **not guaranteed** — it might be longer if the main thread is busy.
3. Minimum timeout delay is **4 ms** (in modern browsers).

---

## 🧪 Bonus: Recursive `setTimeout` for Repeated Tasks

Unlike `setInterval`, this gives better control:

```javascript
function repeat() {
  console.log("Runs every 2 seconds...");
  setTimeout(repeat, 2000);
}

setTimeout(repeat, 2000);
```

---
