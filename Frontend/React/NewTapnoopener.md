## ✅ Example

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
  Visit Example
</a>
```

---

## 🔎 What does it mean?

### 🔸 `target="_blank"`:

Opens the link in a **new tab** or window.

### 🔸 `rel="noopener"`:

Prevents the **new tab** from being able to access your `window` object using `window.opener`.
This **improves security** by preventing attacks like **tabnabbing**.

### 🔸 `rel="noreferrer"`:

* Prevents the browser from **sending the referring page’s URL** (i.e., the `Referer` header is omitted).
* Also includes the behavior of `noopener`.

---

## 🔐 Why use `noopener noreferrer`?

### 1. 🛡️ Security (Avoid Tabnabbing)

Without `noopener`, a malicious site opened in the new tab can **control your page** using `window.opener`:

```js
window.opener.location = 'https://phishing-site.com';
```

This can trick users into thinking they’re still on your site.

### 2. 🔒 Privacy (Avoid sending Referer)

With `noreferrer`, the new site won’t know where the user came from (i.e., no referral information).

---

## ✅ Best Practice

Always use this when linking to external sites in a new tab:

```html
<a href="https://external.com" target="_blank" rel="noopener noreferrer">
  External Site
</a>
```

---

## 🚨 When **not** to use `noreferrer`

If you **need to send referral data** (e.g., for affiliate tracking), you might skip `noreferrer`, but **still use `noopener`**:

```html
<a href="https://affiliate.com" target="_blank" rel="noopener">
  Shop Now
</a>
```

---

## 🧠 Summary

| Attribute             | Purpose                                                       |
| --------------------- | ------------------------------------------------------------- |
| `noopener`            | Protects against tabnabbing (security)                        |
| `noreferrer`          | Hides the referring URL (privacy) and also implies `noopener` |
| Always with `_blank`? | ✅ Yes, it’s a best practice                                   |

---

