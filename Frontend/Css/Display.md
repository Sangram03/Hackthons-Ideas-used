## 🧭 What is `display` in CSS?

The `display` property controls:

* **Whether an element is block or inline**
* **How children are arranged** (e.g., with `flex`, `grid`)
* **Whether the element participates in layout at all**

---

## ✅ Common `display` Values (with examples)

### 1. 🔹 `block`

* Takes **full width** available
* Starts on a **new line**
* Respects **width, height, margin, padding**

```css
div {
  display: block;
}
```

🧱 Examples: `<div>`, `<section>`, `<p>`

---

### 2. 🔹 `inline`

* Takes **only as much width as needed**
* **Does not** start on a new line
* Ignores `width` and `height` settings

```css
span {
  display: inline;
}
```

🧵 Examples: `<span>`, `<a>`, `<strong>`

---

### 3. 🔹 `inline-block`

* Like `inline`, but **supports width & height**

```css
button {
  display: inline-block;
  width: 100px;
}
```

💡 Used for custom buttons or styled inline elements

---

### 4. 🔹 `none`

* **Hides** the element completely
* It’s removed from the document flow (not visible, no space)

```css
div {
  display: none;
}
```

🧼 Useful for conditional content (e.g., toggling modals, tabs)

---

### 5. 🔹 `flex`

* Turns the container into a **flexbox layout**
* Children become **flex items**

```css
.container {
  display: flex;
}
```

🔧 Used for horizontal or vertical alignment and layout

---

### 6. 🔹 `inline-flex`

* Like `flex`, but container behaves as **inline element**

```css
.container {
  display: inline-flex;
}
```

📦 Useful when you want flex behavior without breaking the inline flow

---

### 7. 🔹 `grid`

* Turns the container into a **grid layout**
* Children are placed in **rows and columns**

```css
.container {
  display: grid;
}
```

🔲 Ideal for complex layouts with multiple dimensions

---

### 8. 🔹 `inline-grid`

* Like `grid`, but inline behavior

```css
.container {
  display: inline-grid;
}
```

---

### 9. 🔹 `table`, `table-row`, `table-cell`, etc.

* Makes any element behave like a **table structure**

```css
.container {
  display: table;
}
.row {
  display: table-row;
}
.cell {
  display: table-cell;
}
```

📋 Good for fallback layout or mimicking table behavior without actual `<table>` tags

---

### 10. 🔹 `contents`

* Removes the element's box but **keeps its children**
* Children act as if they are direct children of the parent

```css
.wrapper {
  display: contents;
}
```

⚠️ Not supported in some older browsers. No visual box for `.wrapper`.

---

## 📌 Summary Table

| Display Value  | Block-like?   | Can Set Width/Height? | Starts New Line? | Layout Behavior  |
| -------------- | ------------- | --------------------- | ---------------- | ---------------- |
| `block`        | ✅             | ✅                     | ✅                | Full width       |
| `inline`       | ❌             | ❌                     | ❌                | Inline text flow |
| `inline-block` | ❌             | ✅                     | ❌                | Hybrid           |
| `none`         | ❌ (invisible) | ❌                     | ❌                | Hidden           |
| `flex`         | ✅             | ✅                     | ✅                | Flex layout      |
| `inline-flex`  | ❌             | ✅                     | ❌                | Inline + flex    |
| `grid`         | ✅             | ✅                     | ✅                | Grid layout      |
| `inline-grid`  | ❌             | ✅                     | ❌                | Inline + grid    |
| `table`        | ✅             | ✅                     | ✅                | Table layout     |
| `contents`     | N/A           | ❌                     | ❌                | Removes box      |

---

## 🧠 Tips

* Use `flex` or `grid` for modern layouts (easier and more powerful than floats or tables).
* Use `display: none` to hide elements (but remember: it’s **not accessible**).
* Inline elements can't have padding/margin affecting layout the same way block elements can.
* `inline-block` is great when you want a compact block-level item (like buttons).

---

