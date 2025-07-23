## 🪟 `window.open()` — What Is It?

`window.open()` is a built-in JavaScript method that **opens a new browser window or tab**.

### ✅ Syntax:

```js
window.open(url, target, features);
```

### ✅ Parameters:

| Parameter  | Type     | Description                                                          |
| ---------- | -------- | -------------------------------------------------------------------- |
| `url`      | `string` | (Optional) The URL to open. If empty, opens a blank page.            |
| `target`   | `string` | (Optional) Specifies where to open the URL (e.g., `_blank`, `_self`) |
| `features` | `string` | (Optional) Comma-separated settings like size, scrollbars, etc.      |

---

## 🔹 Example 1: Open a new tab

```js
window.open("https://example.com", "_blank");
```

* Opens `example.com` in a **new tab** (`_blank`).

---

## 🔹 Example 2: Open in the same window

```js
window.open("https://example.com", "_self");
```

* Navigates the **current tab** to `example.com`.

---

## 🔹 Example 3: Open a popup window with features

```js
window.open("https://example.com", "_blank", "width=600,height=400,scrollbars=yes");
```

* Opens a **popup window** with the given size and scrollbars.

> ⚠️ Pop-up blockers may prevent it unless triggered by **user interaction** (like `onClick`).

---

## 🔸 Common `target` Values

| Value     | Behavior                             |
| --------- | ------------------------------------ |
| `_blank`  | Opens in a new window/tab            |
| `_self`   | Opens in the same tab                |
| `_parent` | Opens in the parent frame            |
| `_top`    | Opens in the full body of the window |

---

## 🛠️ Common `features` Values (for popups)

| Feature          | Description                  |
| ---------------- | ---------------------------- |
| `width=600`      | Width in pixels              |
| `height=400`     | Height in pixels             |
| `resizable=yes`  | Can user resize the window?  |
| `scrollbars=yes` | Are scrollbars enabled?      |
| `top=100`        | Position from top of screen  |
| `left=200`       | Position from left of screen |

Example:

```js
window.open("https://example.com", "_blank", "width=500,height=400,resizable=no");
```

---

## 🔁 Related `window` Functions

| Function               | Description                                                            |
| ---------------------- | ---------------------------------------------------------------------- |
| `window.close()`       | Closes the current or a referenced window (if opened by `window.open`) |
| `window.print()`       | Opens the print dialog                                                 |
| `window.alert()`       | Displays an alert dialog                                               |
| `window.confirm()`     | Shows a confirmation dialog (OK/Cancel)                                |
| `window.prompt()`      | Asks for input with a prompt box                                       |
| `window.location.href` | Gets or sets current URL                                               |
| `window.scrollTo(x,y)` | Scrolls window to coordinates                                          |

---

## ❗ Security Considerations

* Modern browsers may block `window.open()` if:

  * It’s not triggered by a **user event** (like a button click).
  * The page tries to open too many popups (spam prevention).
* Many sites use it carefully for:

  * Payment gateways
  * External redirects
  * Print previews

---

## ✅ Example in React

```jsx
<button onClick={() => window.open("https://openai.com", "_blank")}>
  Open OpenAI
</button>
```

---

