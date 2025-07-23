### ✅ `window.location.href` – Full Explanation

`window.location.href` is a JavaScript property used to **get or set the URL of the current page**.

---

## 📌 Syntax

```js
// Get the current URL
console.log(window.location.href);

// Set a new URL (redirect the user)
window.location.href = "https://example.com";
```

---

## 🔍 1. **Get the Current Page URL**

```js
console.log(window.location.href);
```

This will log the **entire URL** in the browser’s address bar, e.g.:

```
https://yourwebsite.com/products?page=2
```

---

## 🔁 2. **Redirect the User to Another Page**

```js
window.location.href = "https://google.com";
```

This will **navigate** the browser to a new page — similar to clicking a link or form submission.

---

## 💡 Use Case in React

You can use it for simple redirects **outside** of React Router:

```js
const handleLogout = () => {
  localStorage.clear();
  window.location.href = "/login"; // redirects to login page
};
```

---

## 🔧 Other Related `window.location` Properties

| Property                   | Description                                 |
| -------------------------- | ------------------------------------------- |
| `window.location.href`     | Full URL (can get or set)                   |
| `window.location.hostname` | Just the domain (e.g., `example.com`)       |
| `window.location.pathname` | Just the path (e.g., `/products/123`)       |
| `window.location.protocol` | Protocol used (e.g., `https:`)              |
| `window.location.port`     | Port (e.g., `3000` if running on localhost) |
| `window.location.search`   | Query string (e.g., `?page=2&sort=asc`)     |
| `window.location.hash`     | Hash fragment (e.g., `#section1`)           |

---

## ⚠️ Things to Keep in Mind

* When you set `window.location.href`, it **reloads** the page.
* If you're using **React Router**, use `useNavigate()` or `<Navigate />` instead for **client-side navigation** (without full page reload).
* `window.location.href = "/somepath"` behaves like an anchor tag click.

---

## ✅ Example: Redirect After 3 Seconds

```js
setTimeout(() => {
  window.location.href = "/thank-you";
}, 3000);
```

Redirects the user to `/thank-you` after 3 seconds.

---

