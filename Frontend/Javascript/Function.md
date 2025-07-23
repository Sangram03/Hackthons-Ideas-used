## 🧠 What is a Function?

A **function** is a block of reusable code that performs a specific task. You define a function **once** and can **use (call)** it many times.

---

## ✅ Basic Syntax:

```javascript
function functionName(parameters) {
  // code to execute
  return result;
}
```

### Example:

```javascript
function greet(name) {
  return "Hello, " + name;
}

console.log(greet("Sangram")); // "Hello, Sangram"
```

---

## 🧩 Function Types in JavaScript

### 1. **Function Declaration (Named Function)**

```javascript
function add(a, b) {
  return a + b;
}
```

> ✅ Hoisted (can be called before they are defined)

---

### 2. **Function Expression**

```javascript
const add = function(a, b) {
  return a + b;
};
```

> ❌ Not hoisted (must be defined before calling)

---

### 3. **Arrow Function (ES6)**

```javascript
const add = (a, b) => a + b;
```

More concise and **doesn't bind `this`** (great for callbacks and methods inside objects).

---

### 4. **Anonymous Function**

A function **without a name**, usually used as a **callback**:

```javascript
setTimeout(function() {
  console.log("Executed after 2 seconds");
}, 2000);
```

---

### 5. **Immediately Invoked Function Expression (IIFE)**

Executes right after it’s defined:

```javascript
(function () {
  console.log("This runs immediately!");
})();
```

---

### 6. **Async Function**

Allows use of `await` inside it:

```javascript
async function fetchData() {
  const res = await fetch("https://api.example.com/data");
  const data = await res.json();
  return data;
}
```

---

## 🧪 Parameters vs Arguments

* **Parameters**: Variables in function definition
* **Arguments**: Actual values passed during call

```javascript
function greet(name) { // name = parameter
  return "Hi " + name;
}

greet("John"); // "John" = argument
```

---

## 🔁 Return vs Console.log

```javascript
function sayHi() {
  return "Hi"; // sends value to caller
}

console.log(sayHi()); // displays it in console
```

---

## 🌟 Default Parameters

```javascript
function greet(name = "Guest") {
  return "Hello, " + name;
}

greet(); // "Hello, Guest"
```

---

## 🧩 Rest Parameters

Collects all remaining arguments into an array:

```javascript
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}

sum(1, 2, 3); // 6
```

---

## 🔀 Callback Functions

You can **pass a function as an argument** to another function:

```javascript
function processUserInput(callback) {
  const name = "Sangram";
  callback(name);
}

processUserInput(function(name) {
  console.log("Hello " + name);
});
```

---

## 📦 Function Scope

Variables declared inside a function are **local** to that function:

```javascript
function test() {
  let localVar = "Only inside";
  console.log(localVar);
}
```

---

## 🔁 Nested Functions (Closure Example)

```javascript
function outer() {
  let outerVar = "I’m outer";

  function inner() {
    console.log(outerVar); // Accesses outerVar
  }

  return inner;
}

const myFunc = outer();
myFunc(); // "I’m outer"
```

This is called a **closure** — a powerful feature in JS.

---

## ✅ Best Practices

* Use `const` for function expressions
* Use arrow functions for short callbacks
* Prefer named functions for clarity
* Keep functions small and focused (Single Responsibility)
* Use `return` to pass values, not `console.log`

---

## ❓Want Examples On:

* How functions behave in **objects**
* Real-world use (like React/Node apps)
* Recursion or higher-order functions

