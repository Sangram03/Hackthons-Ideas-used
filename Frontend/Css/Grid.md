## 🔲 What is CSS Grid?

**CSS Grid** is a **two-dimensional layout system** (rows + columns) that allows you to **create complex responsive layouts** easily.

It works by defining a container (`display: grid`) and placing items inside it according to a **grid structure**.

---

## 🧱 Basic Terminology

| Term           | Meaning                                             |
| -------------- | --------------------------------------------------- |
| Grid Container | The element with `display: grid`                    |
| Grid Item      | The direct children of the grid container           |
| Grid Line      | The dividing lines between rows/columns             |
| Grid Cell      | The space between two adjacent row and column lines |
| Grid Track     | A row or column                                     |
| Grid Area      | A rectangular area made up of one or more cells     |

---

## ✅ Basic Syntax

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px;
  grid-template-rows: 100px 100px;
}
```

```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

📦 This creates a **2x2 grid** with fixed sizes.

---

## 🎯 Grid Properties

### 🔹 On Grid **Container**:

| Property                            | Description                                         |
| ----------------------------------- | --------------------------------------------------- |
| `display: grid`                     | Enables grid layout                                 |
| `grid-template-columns`             | Defines column sizes (e.g., `200px`, `1fr`, `auto`) |
| `grid-template-rows`                | Defines row sizes                                   |
| `gap` / `row-gap` / `column-gap`    | Adds space between grid items                       |
| `grid-template-areas`               | Names areas in the layout                           |
| `justify-items` / `align-items`     | Aligns content inside grid cells                    |
| `justify-content` / `align-content` | Aligns the whole grid within the container          |

---

### 🔹 On Grid **Items**:

| Property       | Description                              |
| -------------- | ---------------------------------------- |
| `grid-column`  | Span or place columns (`1 / 3`)          |
| `grid-row`     | Span or place rows                       |
| `grid-area`    | Refers to a named area from the template |
| `justify-self` | Aligns one item horizontally             |
| `align-self`   | Aligns one item vertically               |

---

## 📏 Units Used

| Unit               | Meaning                     |
| ------------------ | --------------------------- |
| `px`, `%`          | Fixed or relative length    |
| `fr`               | Fraction of remaining space |
| `auto`             | Size based on content       |
| `minmax(min, max)` | Flexible size range         |

```css
grid-template-columns: 1fr 2fr; /* 1 part + 2 parts */
grid-template-columns: repeat(3, 1fr); /* 3 equal columns */
```

---

## 🧩 Example: 3-column Layout

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  gap: 20px;
}
```

---

## 🔄 Spanning Columns and Rows

```css
.item {
  grid-column: 1 / 3; /* spans column 1 and 2 */
  grid-row: 1 / 2;
}
```

---

## 🧠 Named Grid Areas

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 1fr 3fr;
  grid-template-rows: auto 1fr auto;
}
```

```css
.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

```html
<div class="container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main</div>
  <div class="footer">Footer</div>
</div>
```

---

## 🔀 Alignment in Grid

| Property          | Usage                                  | Values                              |
| ----------------- | -------------------------------------- | ----------------------------------- |
| `justify-items`   | Align items **horizontally**           | `start`, `center`, `end`, `stretch` |
| `align-items`     | Align items **vertically**             | Same                                |
| `justify-content` | Align **grid as a whole** horizontally |                                     |
| `align-content`   | Align **grid as a whole** vertically   |                                     |

---

## 🎯 Responsive Grid with `auto-fit` and `minmax`

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}
```

💡 This allows the grid to **automatically adjust** the number of columns based on screen size.

---

## 📚 Summary

| Concept           | Description                 |
| ----------------- | --------------------------- |
| `display: grid`   | Turns container into a grid |
| `grid-template-*` | Defines layout size         |
| `gap`             | Adds spacing                |
| `fr`              | Flexible layout unit        |
| `auto-fit/minmax` | Responsive grids            |
| `grid-area`       | Named layout regions        |

---
