## 🔍 What is React Context?

React Context provides a way to pass data through the component tree **without having to pass props down manually at every level**.

It is best used for **global state** like:

* Authentication status
* Theme (light/dark)
* User data
* Language settings
* Shopping cart contents
* Application-wide alerts or modals
* Credits, image data, etc. (as you're using in your app)

---

## 🧠 Basic Concepts

React Context has **3 main parts**:

1. **`React.createContext()`** – creates the context
2. **Provider** – the component that wraps and provides the data
3. **Consumer or `useContext` hook** – to access the context data inside components

---

## ✅ Basic Example: Theme Context

```jsx
// ThemeContext.js
import React, { createContext, useState } from "react";

export const ThemeContext = createContext();

export const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState("light");

  const toggleTheme = () =>
    setTheme((prev) => (prev === "light" ? "dark" : "light"));

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};
```

```jsx
// App.js
import React, { useContext } from "react";
import { ThemeProvider, ThemeContext } from "./ThemeContext";

const ThemedComponent = () => {
  const { theme, toggleTheme } = useContext(ThemeContext);

  return (
    <div style={{ background: theme === "light" ? "#fff" : "#333", color: "#000" }}>
      <p>Current Theme: {theme}</p>
      <button onClick={toggleTheme}>Toggle</button>
    </div>
  );
};

export default function App() {
  return (
    <ThemeProvider>
      <ThemedComponent />
    </ThemeProvider>
  );
}
```

---

## ⚙️ When Should You Use Context?

### ✅ Good Use Cases:

* **Authentication/Logged-in user data**
* **Global UI state** (modals, toasts)
* **User preferences** (dark/light mode, language)
* **Multi-step form data**
* **Credit management (like in your app)**

### 🚫 Don’t Use Context For:

* Passing data between just **parent and immediate child**
* **Frequently changing data** (like typing input)
* **Performance-heavy state** (consider `Redux`, `Zustand`, etc.)

---

## 🧩 Real Use Case (from your app): Credits Context

```jsx
// AppContext.jsx
import { createContext, useState } from "react";

export const AppContext = createContext();

const AppContextProvider = ({ children }) => {
  const [credit, setCredit] = useState(10);
  const [image, setImage] = useState(null);

  return (
    <AppContext.Provider value={{ credit, setCredit, image, setImage }}>
      {children}
    </AppContext.Provider>
  );
};

export default AppContextProvider;
```

```jsx
// In your main index.js or App.jsx
import AppContextProvider from './context/AppContext';

<React.StrictMode>
  <BrowserRouter>
    <AppContextProvider>
      <App />
    </AppContextProvider>
  </BrowserRouter>
</React.StrictMode>
```

```jsx
// Inside any component
import { useContext } from "react";
import { AppContext } from "../context/AppContext";

const Dashboard = () => {
  const { credit, setCredit } = useContext(AppContext);

  return (
    <div>
      <h1>Your Credits: {credit}</h1>
      <button onClick={() => setCredit(credit - 1)}>Use 1 Credit</button>
    </div>
  );
};
```

---

## 📌 Summary

| Feature           | Description                                 |
| ----------------- | ------------------------------------------- |
| `createContext()` | Creates a context object                    |
| `Provider`        | Wraps your component tree and provides data |
| `useContext()`    | Lets you consume the data                   |

---

