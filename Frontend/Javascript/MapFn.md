## 🧭 What is `map()` in JavaScript?

The `map()` function is a **built-in array method** that:

* Loops through each item in an array
* Applies a **callback function** to each item
* Returns a **new array** with the **transformed values**
* ✅ Does **not modify** the original array

---

## ✅ Syntax

```javascript
array.map(function(currentValue, index, array) {
  // return something
});
```

or with arrow function:

```javascript
array.map((currentValue, index, array) => {
  // return something
});
```

| Parameter          | Description                      |
| ------------------ | -------------------------------- |
| `currentValue`     | The current item being processed |
| `index` (optional) | The index of the current item    |
| `array` (optional) | The entire array being mapped    |

---

## 📦 Simple Example

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);

console.log(doubled); // [2, 4, 6, 8]
```

💡 Here, we multiplied each number by 2. The original array remains unchanged.

---

## 🧰 Use Cases

### 🔸 1. Transform array values

```javascript
const prices = [100, 200, 300];
const withTax = prices.map(p => p * 1.18); // 18% GST

console.log(withTax); // [118, 236, 354]
```

---

### 🔸 2. Extract properties from objects

```javascript
const users = [
  { id: 1, name: 'Sangram' },
  { id: 2, name: 'Rahul' },
];

const names = users.map(user => user.name);

console.log(names); // ['Sangram', 'Rahul']
```

---

### 🔸 3. Add new properties

```javascript
const products = [
  { name: 'Pen', price: 10 },
  { name: 'Book', price: 100 },
];

const updatedProducts = products.map(p => ({
  ...p,
  inStock: true,
}));

console.log(updatedProducts);
/*
[
  { name: 'Pen', price: 10, inStock: true },
  { name: 'Book', price: 100, inStock: true }
]
*/
```

---

## ⚠️ Important Notes

* `map()` **always returns a new array**
* Does **not mutate** the original array
* You **must return** something inside the callback (or you'll get `undefined`)

---

## 🧪 `map()` vs `forEach()`

| Feature           | `map()`                            | `forEach()`                      |
| ----------------- | ---------------------------------- | -------------------------------- |
| Returns new array | ✅ Yes                              | ❌ No (undefined)                 |
| Modifies original | ❌ No                               | ❌ No                             |
| Use case          | To **transform** and get new array | To **perform side effects** only |

---

## 🧠 Real-World Example

You fetch data from an API and want to show just names:

```javascript
const apiData = [
  { id: 1, username: 'john123' },
  { id: 2, username: 'jane456' },
];

const usernames = apiData.map(user => user.username);

console.log(usernames); // ['john123', 'jane456']
```

---

