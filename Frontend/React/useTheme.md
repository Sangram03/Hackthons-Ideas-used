### 🔧 Full Code Snippet:

```js
export const useTheme = () => {
  const [isDark, setIsDark] = useState(() => {
    const saved = localStorage.getItem('theme');
    return saved === 'dark' || (!saved && window.matchMedia('(prefers-color-scheme: dark)').matches);
  });
};
```

---

## ✅ What is `useTheme`?

* This is a **custom React hook**.
* It checks and stores the user's **theme preference**: dark mode or light mode.
* It uses:

  * `useState()` to store the current theme
  * `localStorage` to persist the theme setting
  * `window.matchMedia()` to detect the user's OS/browser dark mode preference

---

## 🧠 Line-by-Line Breakdown

### 📦 `export const useTheme = () => { ... }`

* Defines a custom hook called `useTheme` and exports it so it can be used in other files.
* Like any hook, it must start with `use`.

---

### 🧪 `useState(() => { ... })`

```js
const [isDark, setIsDark] = useState(() => {
  ...
});
```

* Initializes a state variable `isDark` that represents whether dark mode is on.
* The `setIsDark` function allows updating it.
* The function inside `useState()` is called **lazily** only on the first render — useful for reading from localStorage.

---

### 🧾 `const saved = localStorage.getItem('theme');`

* Retrieves the saved theme (either `'dark'`, `'light'`, or `null`) from the browser's local storage.
* `localStorage` keeps data between page reloads or browser restarts.

---

### 🌓 `return saved === 'dark' || (!saved && window.matchMedia(...).matches);`

This line determines whether to start in dark mode:

#### Breakdown:

```js
saved === 'dark'
```

* If user explicitly saved `'dark'` in localStorage → returns `true`.

```js
!saved && window.matchMedia('(prefers-color-scheme: dark)').matches
```

* If **no theme was saved**, then check if the **system/browser prefers dark mode** using `window.matchMedia`.

📘 `window.matchMedia('(prefers-color-scheme: dark)').matches` is `true` if the user's device or browser is set to dark mode.

---

### ✅ Final Meaning:

The `isDark` state is `true` if:

* The user saved `"dark"` as their theme in `localStorage`, OR
* No theme was saved, but their system prefers dark mode

---

### 🛠 Example Usage in Component:

```js
const MyComponent = () => {
  const [isDark, setIsDark] = useTheme();

  useEffect(() => {
    document.body.className = isDark ? 'dark' : 'light';
  }, [isDark]);

  return (
    <button onClick={() => setIsDark(prev => !prev)}>
      Toggle Theme
    </button>
  );
};
```

---

## 🎯 Summary

| Feature                         | Purpose                                                |
| ------------------------------- | ------------------------------------------------------ |
| `localStorage.getItem('theme')` | Persists user theme between visits                     |
| `window.matchMedia(...)`        | Detects system dark mode                               |
| `useState(() => { ... })`       | Lazily initializes based on saved or system preference |
| `isDark`                        | Boolean: `true` for dark mode, `false` for light       |
| `setIsDark()`                   | Function to update theme                               |

---

