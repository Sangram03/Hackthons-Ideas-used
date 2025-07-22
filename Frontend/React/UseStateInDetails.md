## ✅ What is `useState`?

`useState` is a **React Hook** that lets you add **state variables** to functional components.

In simple words, it allows your component to "remember" things — like form input, toggle status, counters, etc.

---

## 🔧 Syntax

```jsx
const [state, setState] = useState(initialValue);
```

### ✅ Parameters:

* `initialValue`: The default value of the state variable (can be number, string, boolean, object, array, etc.)

### ✅ Returns:

* `state`: The current value of the state.
* `setState`: A function to update that value.

---

## 🧠 Basic Example: Counter

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); // count starts at 0

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={increment}>➕ Increase</button>
      <button onClick={decrement}>➖ Decrease</button>
    </div>
  );
}
```

---

## 🧃 State with String

```jsx
const [name, setName] = useState("Guest");

<input
  type="text"
  value={name}
  onChange={(e) => setName(e.target.value)}
/>

<p>Hello, {name}!</p>
```

---

## 🧊 State with Object

```jsx
const [user, setUser] = useState({ name: "John", age: 25 });

const updateAge = () => {
  setUser({ ...user, age: user.age + 1 }); // spread the previous user
};
```

> Always use spread (`...`) when updating **objects or arrays** to avoid overwriting the entire state.

---

## 🔁 State with Array

```jsx
const [items, setItems] = useState([]);

const addItem = () => {
  setItems([...items, { id: items.length, value: Math.random() * 100 }]);
};
```

---

## 💡 Notes

* Updating state re-renders the component.
* `useState` is only usable **inside functional components** or **custom hooks**.
* If you call `setState` with the same value as before, React skips the re-render.

---

## 🧪 Example Full Component

```jsx
import React, { useState } from "react";

function Example() {
  const [name, setName] = useState("");
  const [count, setCount] = useState(0);

  return (
    <div>
      <input
        placeholder="Type your name"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />
      <h1>Hello, {name || "Stranger"}!</h1>
      
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>➕</button>
      <button onClick={() => setCount(count - 1)}>➖</button>
    </div>
  );
}
```

---

