### 🔗 `NavLink` in React Router — In Detail

`NavLink` is a special version of the `Link` component from `react-router-dom`. It **automatically applies styling (like "active") to the link** when the current route matches the `to` prop.

---

## ✅ Importing `NavLink`

```js
import { NavLink } from 'react-router-dom';
```

---

## 🧩 Basic Usage

```jsx
<NavLink to="/about">About</NavLink>
```

* Works like an anchor tag (`<a>`), but **without refreshing the page**.
* The browser URL updates to `/about`.
* The corresponding `<Route path="/about" />` gets rendered.

---

## 🖌️ Active Class Styling

`NavLink` automatically adds the **`active` class** when the URL matches the link.

```jsx
<NavLink to="/home" className={({ isActive }) => isActive ? "active-link" : ""}>
  Home
</NavLink>
```

### 🔍 Explanation:

* `isActive` is a boolean.
* If the current route matches `/home`, the class `"active-link"` is applied.

---

## 🎯 Full Example with CSS

### `App.jsx`:

```jsx
import { BrowserRouter, Routes, Route, NavLink } from "react-router-dom";
import Home from "./Home";
import About from "./About";
import "./App.css";

function App() {
  return (
    <BrowserRouter>
      <nav>
        <NavLink to="/home" className={({ isActive }) => isActive ? "active" : ""}>Home</NavLink>
        <NavLink to="/about" className={({ isActive }) => isActive ? "active" : ""}>About</NavLink>
      </nav>
      <Routes>
        <Route path="/home" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

### `App.css`:

```css
.active {
  font-weight: bold;
  color: red;
}
```

---

## 🧪 Difference Between `Link` and `NavLink`

| Feature        | `Link`       | `NavLink`                   |
| -------------- | ------------ | --------------------------- |
| Navigation     | ✅ Yes        | ✅ Yes                       |
| Active Styling | ❌ No         | ✅ Yes                       |
| Use Case       | Normal links | Menus, Tabs, Navigation Bar |

---

## ⚙️ NavLink Props

| Prop        | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| `to`        | Path to navigate to (like `/about`)                         |
| `className` | Function to apply class based on `isActive`                 |
| `style`     | Inline style function using `isActive`                      |
| `end`       | Makes exact matching (`/about` doesn’t match `/about/team`) |

---

## 🧠 When to Use

Use `NavLink` when:

* You need to highlight the active page in the UI.
* You’re building a navigation bar or tab system.

---

