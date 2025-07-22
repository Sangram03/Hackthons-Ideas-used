### 🔍 `useEffect` in React – In Depth

`useEffect` is one of the **most important React hooks**. It lets you **run side effects** (e.g., fetch data, update the DOM, set up subscriptions) **after a component renders**.

---

## 🧠 What Is a "Side Effect"?

Side effects are **anything that affects something outside the component**, such as:

* Fetching API data
* Changing the DOM
* Working with timers (`setTimeout`, `setInterval`)
* Subscribing to external events (like sockets, listeners)
* Updating browser title, localStorage, etc.

---

## ✅ Syntax

```jsx
useEffect(() => {
  // your effect here (runs after render)
}, [dependencies]);
```

* The **callback** function runs after the component renders.
* The **dependency array** controls when the effect runs.

---

## 🧪 Basic Example

```jsx
import { useEffect, useState } from "react";

const Timer = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Component rendered or count changed");
  }, [count]);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
    </div>
  );
};
```

---

## 🧯 Cleanup Function

When your component unmounts or dependencies change, you can clean up side effects like this:

```jsx
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Running every second");
  }, 1000);

  return () => {
    clearInterval(interval); // Cleanup when unmounted or before re-running
  };
}, []);
```

---

## 📊 Dependency Array Behavior

| Dependency Array     | When It Runs                                                |
| -------------------- | ----------------------------------------------------------- |
| `[]` (empty)         | Runs once after the first render (like `componentDidMount`) |
| `[value]`            | Runs on first render + whenever `value` changes             |
| No array (dangerous) | Runs after **every render**                                 |

---

## 🧩 Common Use Cases

### 1. ✅ Fetch Data on Mount

```jsx
useEffect(() => {
  const fetchData = async () => {
    const res = await fetch("https://api.example.com/data");
    const json = await res.json();
    console.log(json);
  };

  fetchData();
}, []);
```

---

### 2. 🕓 Set Interval (Timer)

```jsx
useEffect(() => {
  const timer = setInterval(() => {
    console.log("Tick");
  }, 1000);

  return () => clearInterval(timer); // cleanup
}, []);
```

---

### 3. 🎧 Event Listener

```jsx
useEffect(() => {
  const handleResize = () => {
    console.log(window.innerWidth);
  };

  window.addEventListener("resize", handleResize);

  return () => {
    window.removeEventListener("resize", handleResize);
  };
}, []);
```

---

### 4. 🔁 Syncing State with Props or External Data

```jsx
useEffect(() => {
  setFormData(props.userData);
}, [props.userData]);
```

---

## ⚠️ Best Practices

* Always add dependencies to the array (or React will warn you).
* Avoid placing **async/await directly inside `useEffect`**. Use an inner async function.
* Use multiple `useEffect` calls if side effects are unrelated.
* Use cleanup to avoid **memory leaks** in intervals, listeners, or subscriptions.

---

## 💡 Real-World Example (Login Redirect)

```jsx
import { useNavigate } from "react-router-dom";
import { useEffect } from "react";

const Dashboard = ({ isAuthenticated }) => {
  const navigate = useNavigate();

  useEffect(() => {
    if (!isAuthenticated) {
      navigate("/login");
    }
  }, [isAuthenticated]);
};
```

---

## 🧠 TL;DR – `useEffect`

```jsx
useEffect(() => {
  // run on mount or when dependencies change

  return () => {
    // cleanup (optional)
  };
}, [dependencies]);
```

---

