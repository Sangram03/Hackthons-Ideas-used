### 📐 JavaScript `Math` Object – Full Guide

The `Math` object in JavaScript provides built-in **functions** and **constants** for performing **mathematical operations**.

---

## ✅ Basic Usage:

The `Math` object is **not a constructor**, so you **don’t use `new Math()`**. You call its methods directly:

```javascript
Math.methodName(arguments);
```

---

## 🧮 Most Common `Math` Functions:

| Function              | Description                       | Example                         |
| --------------------- | --------------------------------- | ------------------------------- |
| `Math.abs(x)`         | Absolute value                    | `Math.abs(-5)` → `5`            |
| `Math.round(x)`       | Round to nearest integer          | `Math.round(4.7)` → `5`         |
| `Math.floor(x)`       | Round **down** to nearest integer | `Math.floor(4.7)` → `4`         |
| `Math.ceil(x)`        | Round **up** to nearest integer   | `Math.ceil(4.1)` → `5`          |
| `Math.trunc(x)`       | Remove decimal part               | `Math.trunc(4.9)` → `4`         |
| `Math.sqrt(x)`        | Square root                       | `Math.sqrt(9)` → `3`            |
| `Math.pow(x, y)`      | Power (x raised to y)             | `Math.pow(2, 3)` → `8`          |
| `Math.max(a, b, ...)` | Largest value                     | `Math.max(2, 4, 9)` → `9`       |
| `Math.min(a, b, ...)` | Smallest value                    | `Math.min(2, 4, 9)` → `2`       |
| `Math.random()`       | Random float between `0` and `1`  | `Math.random()` → `0.37` (e.g.) |
| `Math.sign(x)`        | Returns `1`, `-1`, `0`, or `-0`   | `Math.sign(-5)` → `-1`          |

---

## 🎲 Random Integer Generator

Get a random number between two values:

```javascript
function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

// Example:
getRandomInt(1, 6); // Random dice roll (1–6)
```

---

## 📌 Useful Constants

| Constant       | Description        | Value           |
| -------------- | ------------------ | --------------- |
| `Math.PI`      | π                  | `3.14159265359` |
| `Math.E`       | Euler’s number     | `2.718`         |
| `Math.LN2`     | Natural log of 2   | `0.693`         |
| `Math.LN10`    | Natural log of 10  | `2.302`         |
| `Math.SQRT2`   | Square root of 2   | `1.414`         |
| `Math.SQRT1_2` | Square root of 1/2 | `0.707`         |

---

## 📏 Trigonometry Functions

| Function          | Description               |
| ----------------- | ------------------------- |
| `Math.sin(x)`     | Sine (x in radians)       |
| `Math.cos(x)`     | Cosine                    |
| `Math.tan(x)`     | Tangent                   |
| `Math.asin(x)`    | Inverse sine              |
| `Math.acos(x)`    | Inverse cosine            |
| `Math.atan(x)`    | Inverse tangent           |
| `Math.atan2(y,x)` | Angle from (0,0) to (x,y) |

```javascript
Math.sin(Math.PI / 2); // 1
```

---

## 🔁 Examples:

```javascript
console.log(Math.abs(-10));       // 10
console.log(Math.round(4.4));     // 4
console.log(Math.ceil(2.1));      // 3
console.log(Math.floor(2.9));     // 2
console.log(Math.pow(2, 3));      // 8
console.log(Math.sqrt(64));       // 8
console.log(Math.max(5, 7, 2));   // 7
console.log(Math.min(5, 7, 2));   // 2
console.log(Math.random());       // 0.0 - 1.0
```

---

## ❓Want More?

I can show you how to:

* Convert degrees ↔ radians
* Create animation effects using `Math`
* Use `Math` in real-world apps (like games or charts)

t me know!
