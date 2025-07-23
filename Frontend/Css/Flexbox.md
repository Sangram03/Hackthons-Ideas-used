## 🧭 What is Flexbox?

**Flexbox** (short for **Flexible Box Layout**) is a layout model that arranges items in **a single axis** — **row** (horizontal) or **column** (vertical) — with powerful options for spacing, alignment, and ordering.

You enable Flexbox by setting:

```css
.container {
  display: flex;
}
```

All **direct children** of `.container` become **flex items**.

---

## 🧱 Key Concepts

| Concept        | Description                                       |
| -------------- | ------------------------------------------------- |
| Flex Container | The parent element with `display: flex`           |
| Flex Items     | The immediate children of the flex container      |
| Main Axis      | The **primary axis**: `row` (default) or `column` |
| Cross Axis     | The axis **perpendicular** to the main axis       |

---

## 🔹 Flex Container Properties

### 1. `display: flex | inline-flex`

* `flex`: block-level flex container
* `inline-flex`: inline-level flex container

---

### 2. `flex-direction`

Defines the direction of the **main axis**.

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

| Value            | Description            |
| ---------------- | ---------------------- |
| `row`            | Left → Right (default) |
| `row-reverse`    | Right → Left           |
| `column`         | Top → Bottom           |
| `column-reverse` | Bottom → Top           |

---

### 3. `flex-wrap`

Allows items to **wrap** to the next line.

```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

| Value          | Description                     |
| -------------- | ------------------------------- |
| `nowrap`       | All items on one line (default) |
| `wrap`         | Items wrap to new lines         |
| `wrap-reverse` | Wrap in reverse order           |

---

### 4. `justify-content` (Main axis alignment)

Aligns items **horizontally** (in row) or **vertically** (in column)

```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

| Value           | Effect                             |
| --------------- | ---------------------------------- |
| `flex-start`    | Items at start of main axis        |
| `center`        | Items centered on main axis        |
| `space-between` | Equal space **between** items      |
| `space-around`  | Equal space **around** items       |
| `space-evenly`  | Equal space **between and around** |

---

### 5. `align-items` (Cross axis alignment)

Aligns items **perpendicular** to the main axis

```css
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

---

### 6. `align-content` (Only when wrapping)

Aligns **rows** of flex items when wrapping

```css
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

---

## 🔸 Flex Item Properties

### 1. `order`

Changes the visual order of the item.

```css
.item {
  order: 1; /* lower = appear first */
}
```

---

### 2. `flex-grow`

Defines how much **extra space** the item should take.

```css
.item {
  flex-grow: 1; /* grow to fill remaining space */
}
```

---

### 3. `flex-shrink`

Defines how the item **shrinks** when space is tight.

```css
.item {
  flex-shrink: 1; /* default: shrink if needed */
}
```

---

### 4. `flex-basis`

Sets the **initial size** of the item **before growing/shrinking**.

```css
.item {
  flex-basis: 200px; /* like width or height */
}
```

---

### 5. `flex` (Shorthand)

```css
.item {
  flex: <grow> <shrink> <basis>;
}

/* Example */
.item {
  flex: 1 1 200px;
}
```

---

### 6. `align-self`

Overrides `align-items` **for a specific item**.

```css
.item {
  align-self: flex-end;
}
```

---

## 🧩 Simple Example

```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.container > div {
  padding: 20px;
  background: lightblue;
  margin: 10px;
}
```

---

## 📚 Summary Table

| Property          | Target    | Purpose                           |
| ----------------- | --------- | --------------------------------- |
| `display: flex`   | container | Enables flex layout               |
| `flex-direction`  | container | Row or column layout              |
| `flex-wrap`       | container | Allow wrapping                    |
| `justify-content` | container | Main axis alignment               |
| `align-items`     | container | Cross axis alignment              |
| `order`           | item      | Reorder items                     |
| `flex`            | item      | Shorthand for grow, shrink, basis |
| `align-self`      | item      | Override individual alignment     |

---

## 🔄 Flexbox vs Grid

| Feature       | Flexbox                 | Grid                        |
| ------------- | ----------------------- | --------------------------- |
| Axis          | One (row or column)     | Two (rows and columns)      |
| Content-based | Yes                     | No (structure-based)        |
| Best for      | Simple, dynamic layouts | Complex, grid-based layouts |

---
