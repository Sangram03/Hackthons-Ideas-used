## 🧭 What is `position` in CSS?

The `position` property specifies how an element is **positioned in the document**. It affects how it is placed relative to:

* the **normal flow**
* its **containing block** (usually the nearest positioned ancestor)
* or the **viewport**

---

## 🔹 Syntax

```css
selector {
  position: static | relative | absolute | fixed | sticky;
  top: value;
  right: value;
  bottom: value;
  left: value;
}
```

---

## ✅ Position Values Explained

### 1. 🔹 `static` (default)

* **Default value** — all elements are `position: static` unless otherwise specified.
* Element is placed **according to normal flow**.
* `top`, `left`, `right`, `bottom` have **no effect**.

```css
div {
  position: static;
}
```

---

### 2. 🔹 `relative`

* Element stays **in the normal document flow**.
* But you can **move it visually** with `top`, `left`, `right`, `bottom`.
* Still takes up space in its original place.

```css
div {
  position: relative;
  top: 10px; /* moves it 10px down */
  left: 20px; /* moves it 20px to the right */
}
```

---

### 3. 🔹 `absolute`

* Removed from normal flow.
* Positioned **relative to the nearest ancestor** with `position: relative/absolute/fixed/sticky`.
* If no such ancestor exists, it positions **relative to `<html>` (the document)**.

```css
div {
  position: absolute;
  top: 0;
  left: 0;
}
```

💡 Used often for dropdowns, modals, tooltips, etc.

---

### 4. 🔹 `fixed`

* Removed from flow (like `absolute`), but **positioned relative to the viewport** (browser window).
* **Stays fixed when scrolling**.

```css
div {
  position: fixed;
  bottom: 10px;
  right: 10px;
}
```

💡 Used for sticky headers, floating buttons, "Back to Top" links, etc.

---

### 5. 🔹 `sticky`

* Acts like `relative` **until a scroll threshold is reached**, then becomes `fixed`.
* Requires a scrollable parent container.
* Needs a `top`, `left`, etc. value to work.

```css
header {
  position: sticky;
  top: 0;
  background: white;
  z-index: 10;
}
```

💡 Great for sticky navigation bars.

---

## 📌 Comparison Table

| Value      | In Document Flow | Relative To                             | Scrolls With Page | Can Use top/left? |
| ---------- | ---------------- | --------------------------------------- | ----------------- | ----------------- |
| `static`   | ✅ Yes            | N/A                                     | ✅ Yes             | ❌ No              |
| `relative` | ✅ Yes            | Itself (original spot)                  | ✅ Yes             | ✅ Yes             |
| `absolute` | ❌ No             | Nearest positioned ancestor or `<html>` | ❌ No              | ✅ Yes             |
| `fixed`    | ❌ No             | Viewport                                | ❌ No              | ✅ Yes             |
| `sticky`   | ✅ Yes (then no)  | Scroll container                        | ✅/❌ Hybrid        | ✅ Yes             |

---

## 🎯 Example Use Case

### Sticky Header:

```css
header {
  position: sticky;
  top: 0;
  background: #fff;
  z-index: 100;
}
```

### Modal Overlay:

```css
.modal {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
}
```

---

## 🔥 Bonus: `z-index` with Positioning

* Only works on **positioned elements** (`relative`, `absolute`, `fixed`, `sticky`)
* Controls **stacking order** — higher `z-index` = on top

```css
.modal {
  position: fixed;
  z-index: 999;
}
```

---

## 🧠 Summary

| Value      | Best For                            |
| ---------- | ----------------------------------- |
| `static`   | Default positioning                 |
| `relative` | Small shifts from original location |
| `absolute` | Tooltips, modals, overlays, etc.    |
| `fixed`    | Floating elements that never move   |
| `sticky`   | Sticky headers, scroll indicators   |

---

