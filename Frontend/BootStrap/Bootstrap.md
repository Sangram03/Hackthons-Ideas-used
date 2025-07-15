## ✅ What is Bootstrap?

Bootstrap is a popular front-end CSS framework that helps you quickly design responsive websites and web applications using ready-made styles and components.

---

## 🔽 1. **Download via CDN (No Installation) — Easiest**

Use this method if you want to **quickly use Bootstrap** without downloading any files.

### ✅ Steps:

1. Open your HTML file.
2. Paste this into your `<head>` section:

```html
<!-- Bootstrap CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

<!-- Optional: Bootstrap JavaScript + Popper -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
```

📌 **No need to install anything. Just an internet connection is required.**

---

## 📦 2. **Install via NPM (For Node.js Projects)**

Use this method if you're working on a project with **Node.js**, **React**, **Vue**, or **Vite**.

### ✅ Install Command:

```bash
npm install bootstrap
```

### ✅ How to Use in Your JS/React App:

In your main JS or React file (like `index.js` or `App.js`):

```js
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
```

---

## 🗂 3. **Download Manually (ZIP)**

Use this method if you're working without Node and want to include files locally.

### ✅ Steps:

1. Go to [https://getbootstrap.com](https://getbootstrap.com)
2. Click on the **Download** button.
3. Choose **Compiled CSS and JS** (ZIP).
4. Extract the ZIP and move the `css` and `js` folders into your project.

### ✅ Add to HTML:

```html
<!-- Bootstrap CSS -->
<link rel="stylesheet" href="css/bootstrap.min.css">

<!-- Bootstrap JS (with Popper) -->
<script src="js/bootstrap.bundle.min.js"></script>
```

---

## 💡 4. **Use Bootstrap with Vite (React/Vue)**

If you use **Vite**, you can follow the same NPM install method:

```bash
npm install bootstrap
```

Then in `main.jsx` or `main.js`:

```js
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
```

---

## 📁 Directory Overview After Manual Download:

```
your-project/
│
├── css/
│   └── bootstrap.min.css
│
├── js/
│   └── bootstrap.bundle.min.js
│
├── index.html
```

---

## 🧪 How to Check It's Working:

In your HTML body, add a test Bootstrap component:

```html
<button class="btn btn-primary">Bootstrap Button</button>
```

If the button appears styled in blue with padding and rounded corners, Bootstrap is working!

---

