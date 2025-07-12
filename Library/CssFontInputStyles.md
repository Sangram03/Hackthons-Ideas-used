## 🎨 Google Fonts Integration Guide

Google Fonts is a free web service that lets you easily use beautiful and modern fonts in your website.

---

### 📌 Step 1: Choose a Font

1. Go to [https://fonts.google.com](https://fonts.google.com)
2. Search and select your desired font (e.g., **Roboto**, **Poppins**, **Montserrat**).
3. Click **"Select this style"**
4. Copy the provided HTML `<link>` or `@import` code.

---

### ✅ Option 1: HTML `<link>` Method (Recommended)

Paste inside the `<head>` of your `index.html`:

```html
<!-- Google Font: Poppins -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
```

---

### ✅ Option 2: CSS `@import` Method

Paste at the **top** of your CSS file:

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
```

---

### 🎯 Step 2: Use the Font in CSS

```css
body {
  font-family: 'Poppins', sans-serif;
}
```

You can also target elements specifically:

```css
h1 {
  font-family: 'Poppins', sans-serif;
  font-weight: 600;
}
```

---

### 🌟 Multiple Fonts Example

```html
<!-- HTML HEAD -->
<link href="https://fonts.googleapis.com/css2?family=Roboto&family=Montserrat:wght@500&display=swap" rel="stylesheet">
```

```css
body {
  font-family: 'Roboto', sans-serif;
}

h2 {
  font-family: 'Montserrat', sans-serif;
}
```

---

### 💡 Tips

* Always specify a **fallback font** like `sans-serif`.
* Use `display=swap` for better performance.
* Load only the weights/styles you need to reduce load time.

---

### 📚 Resources

* 🔗 [Google Fonts](https://fonts.google.com)
* 📘 [How to Use Google Fonts](https://developers.google.com/fonts/docs/getting_started)

---

