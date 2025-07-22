`useNavigate` is a hook provided by **React Router v6+** to programmatically **navigate between routes** in your React app.

---

## 🔁 What is `useNavigate`?

`useNavigate` lets you **navigate to different pages (routes)** from inside your components **without using `<Link>`** or `<NavLink>`.

It replaces the older `useHistory().push()` used in React Router v5.

---

## 🧠 Syntax

```js
import { useNavigate } from 'react-router-dom';

const navigate = useNavigate();

navigate("/path"); // Navigates to /path
```

---

## ✅ Basic Example

```jsx
import React from "react";
import { useNavigate } from "react-router-dom";

const Home = () => {
  const navigate = useNavigate();

  const goToAbout = () => {
    navigate("/about");
  };

  return (
    <div>
      <h1>Home Page</h1>
      <button onClick={goToAbout}>Go to About</button>
    </div>
  );
};

export default Home;
```

---

## 🔄 Navigate with State

You can also pass **data between pages** like this:

```js
navigate("/profile", { state: { userId: 123 } });
```

Then access it in the destination component using:

```js
import { useLocation } from "react-router-dom";

const location = useLocation();
console.log(location.state.userId); // 123
```

---

## 🔙 Navigate Back / Forward

```js
navigate(-1); // Go back
navigate(1);  // Go forward
```

---

## 📌 useNavigate Options

```js
navigate("/login", {
  replace: true,  // replaces the current entry in the history stack
  state: { from: "dashboard" }, // optional state
});
```

| Option    | Description                                                                  |
| --------- | ---------------------------------------------------------------------------- |
| `replace` | If `true`, it replaces the current history entry instead of adding a new one |
| `state`   | Any object you want to pass to the next route                                |

---

## 📦 Full Use Case: Protected Route

```jsx
const Dashboard = () => {
  const { isLoggedIn } = useAuth(); // some auth logic
  const navigate = useNavigate();

  useEffect(() => {
    if (!isLoggedIn) {
      navigate("/login", { replace: true });
    }
  }, [isLoggedIn]);

  return <div>Dashboard Content</div>;
};
```

---

## 🧩 Common Use Cases

| Scenario                                                   | Solution using `useNavigate` |
| ---------------------------------------------------------- | ---------------------------- |
| Redirect after form submit                                 | `navigate('/success')`       |
| Redirect user to login if not authenticated                | `navigate('/login')`         |
| Programmatic routing from logic (e.g. button, timer, etc.) | `navigate('/home')`          |

---

## ⚠️ Notes

* Only works inside components **wrapped in `<BrowserRouter>`**.
* Works with both relative and absolute paths.
* For query params, use `searchParams` from `useLocation` or manually construct.

---

## 📍 TL;DR

```jsx
const navigate = useNavigate();
navigate("/about");                   // Go to /about
navigate(-1);                         // Go back
navigate("/login", { replace: true }); // Replace current route
navigate("/profile", { state: { id: 5 } }); // Pass state
```

---

