The **rest operator (`...`)** in JavaScript is used to **collect multiple elements** into a **single array** or object. It looks just like the **spread operator (`...`)**, but the **use case is opposite**.

---

## ✅ Purpose of Rest Operator

> The rest operator **gathers** items into one variable.
> Spread **expands**, while rest **collects**.

---

## 🧠 Syntax

```js
function myFunc(...args) {
  console.log(args);
}
```

---

## 📌 Where You Can Use Rest:

### 1. **In Function Parameters** (to gather all arguments into an array)

```js
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3)); // 6
```

🔍 `numbers` becomes `[1, 2, 3]`

---

### 2. **With Destructuring Arrays**

```js
const [first, ...rest] = [10, 20, 30, 40];

console.log(first); // 10
console.log(rest);  // [20, 30, 40]
```

---

### 3. **With Destructuring Objects**

```js
const user = { name: 'Sangram', age: 23, country: 'India' };
const { name, ...rest } = user;

console.log(name); // 'Sangram'
console.log(rest); // { age: 23, country: 'India' }
```

---

## 🆚 Rest vs Spread

| Feature  | **Rest (`...`)**                      | **Spread (`...`)**                       |
| -------- | ------------------------------------- | ---------------------------------------- |
| Role     | Collects values into an array/object  | Spreads values out                       |
| Use case | In function parameters, destructuring | In array/object literals, function calls |
| Position | Must be last in parameter list        | Can be anywhere                          |
| Example  | `function(...args) {}`                | `console.log(...args)`                   |

---

## 🧪 Example: Mixing Both

```js
function greet(first, ...others) {
  console.log("First:", first);
  console.log("Others:", others);
}

greet("A", "B", "C");

// First: A
// Others: ["B", "C"]
```

---

## ⚠️ Rules & Notes

* Only one rest parameter is allowed in a function.
* It **must be the last** parameter in the function.
* It works only with iterable values (arrays, objects).

---

## ✅ Real-world Example

```js
const logUserData = ({ name, ...details }) => {
  console.log("Name:", name);
  console.log("Details:", details);
};

logUserData({ name: "Sangram", age: 22, role: "Dev" });

// Name: Sangram
// Details: { age: 22, role: "Dev" }
```

