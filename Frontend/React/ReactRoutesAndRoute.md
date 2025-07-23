## 🧭 What is React Router?

**React Router** is a standard routing library for React. It allows you to:

* Define routes for different components
* Navigate between pages using URLs
* Handle nested layouts and dynamic paths

---

## 🧩 `Routes` and `Route` Overview

| Element  | Purpose                                              |
| -------- | ---------------------------------------------------- |
| `Routes` | A wrapper that contains all your route definitions   |
| `Route`  | Defines a mapping between a URL path and a component |

---

## ✅ Basic Example

```jsx
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Home from './pages/Home';
import About from './pages/About';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

### In this example:

* `/` → renders the `Home` component
* `/about` → renders the `About` component

---

## 🔁 Important Props

### `path`

Defines the URL to match.

```jsx
<Route path="/login" element={<Login />} />
```

### `element`

Specifies the component to render when the route matches.

```jsx
<Route path="/dashboard" element={<Dashboard />} />
```

---

## 🔄 Dynamic Routes (e.g., `/product/123`)

```jsx
<Route path="/product/:id" element={<Product />} />
```

Then inside `Product.jsx`:

```jsx
import { useParams } from "react-router-dom";

const Product = () => {
  const { id } = useParams(); // id = "123"
  return <h2>Product ID: {id}</h2>;
};
```

---

## 🧬 Nested Routes

You can nest routes inside a parent layout:

```jsx
<Route path="/dashboard" element={<DashboardLayout />}>
  <Route path="profile" element={<Profile />} />
  <Route path="settings" element={<Settings />} />
</Route>
```

### URL Mapping:

* `/dashboard/profile` → `Profile` inside `DashboardLayout`
* `/dashboard/settings` → `Settings` inside `DashboardLayout`

Inside `DashboardLayout`:

```jsx
import { Outlet } from "react-router-dom";

const DashboardLayout = () => (
  <div>
    <h1>Dashboard</h1>
    <Outlet /> {/* renders nested routes here */}
  </div>
);
```

---

## 🔄 Redirect (Navigate)

To redirect programmatically:

```jsx
import { useNavigate } from "react-router-dom";

const Login = () => {
  const navigate = useNavigate();
  const handleLogin = () => {
    // after login
    navigate('/dashboard');
  };

  return <button onClick={handleLogin}>Login</button>;
};
```

---

## 🛠 404 Not Found Route

```jsx
<Route path="*" element={<NotFound />} />
```

This will match **any undefined route**.

---

## 🧪 Summary Table

| Syntax                                  | Purpose                             |
| --------------------------------------- | ----------------------------------- |
| `<Routes>`                              | Wrapper for route definitions       |
| `<Route path="/" element={<Home />} />` | Maps URL path to component          |
| `useParams()`                           | Get route parameters (e.g., `:id`)  |
| `useNavigate()`                         | Programmatically navigate to routes |
| `<Outlet />`                            | Renders nested route content        |

---

## ✅ Full Example Setup

```jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Home from './Home';
import About from './About';
import Contact from './Contact';
import NotFound from './NotFound';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
        <Route path="*" element={<NotFound />} />
      </Routes>
    </BrowserRouter>
  );
}
```

---

Let me know if you want:

* Protected/private routes (auth)
* Code splitting (lazy loading)
* React Router + query params (`useSearchParams`)
* React Router + Context/Redux integration
