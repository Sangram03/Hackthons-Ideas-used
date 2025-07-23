## 🔹 1. **Basic Selectors**

| Selector  | Description                      | Example                   |
| --------- | -------------------------------- | ------------------------- |
| `*`       | Universal selector (selects all) | `* { margin: 0; }`        |
| `element` | Type/tag selector                | `p { font-size: 16px; }`  |
| `#id`     | ID selector                      | `#header { color: red; }` |
| `.class`  | Class selector                   | `.btn { padding: 10px; }` |

---

## 🔹 2. **Group & Combinator Selectors**

### 🔸 Grouping:

```css
h1, h2, p { margin-bottom: 10px; }
```

### 🔸 Combinators:

| Selector | Meaning              | Example                            |
| -------- | -------------------- | ---------------------------------- |
| `A B`    | Descendant of A      | `div p` (all `<p>` inside `<div>`) |
| `A > B`  | Direct child of A    | `ul > li`                          |
| `A + B`  | Immediately after A  | `h1 + p`                           |
| `A ~ B`  | Any siblings after A | `h1 ~ p`                           |

---

## 🔹 3. **Attribute Selectors**

| Selector          | Meaning                                | Example                         |          |          |
| ----------------- | -------------------------------------- | ------------------------------- | -------- | -------- |
| `[attr]`          | Has attribute                          | `input[type]`                   |          |          |
| `[attr="value"]`  | Exact match                            | `input[type="text"]`            |          |          |
| `[attr~="value"]` | Space-separated value contains `value` | `[title~="flower"]`             |          |          |
| \`\[attr          | ="value"]\`                            | Starts with `value` or `value-` | \`\[lang | ="en"]\` |
| `[attr^="value"]` | Starts with `value`                    | `a[href^="https"]`              |          |          |
| `[attr$="value"]` | Ends with `value`                      | `img[src$=".jpg"]`              |          |          |
| `[attr*="value"]` | Contains `value` anywhere              | `a[href*="google"]`             |          |          |

---

## 🔹 4. **Pseudo-classes**

These target elements based on **state** or **position**.

| Selector                 | Description                              | Example            |
| ------------------------ | ---------------------------------------- | ------------------ |
| `:hover`                 | When hovered                             | `button:hover`     |
| `:active`                | When clicked                             | `a:active`         |
| `:focus`                 | When focused                             | `input:focus`      |
| `:first-child`           | First child of parent                    | `li:first-child`   |
| `:last-child`            | Last child                               | `li:last-child`    |
| `:nth-child(n)`          | Specific nth child                       | `li:nth-child(2)`  |
| `:nth-of-type(n)`        | Specific nth of its type                 | `p:nth-of-type(2)` |
| `:not(selector)`         | Negation                                 | `div:not(.active)` |
| `:checked`               | Checked checkbox/radio                   | `input:checked`    |
| `:disabled` / `:enabled` | Form control state                       | `input:disabled`   |
| `:empty`                 | No children or text                      | `div:empty`        |
| `:first-of-type`         | First element of its type among siblings | `p:first-of-type`  |
| `:only-child`            | Only child of its parent                 | `div:only-child`   |

---

## 🔹 5. **Pseudo-elements**

Used to **style specific parts** of an element.

| Selector         | Description                   | Example                                |
| ---------------- | ----------------------------- | -------------------------------------- |
| `::before`       | Insert content before element | `p::before { content: "★"; }`          |
| `::after`        | Insert content after element  | `p::after { content: "✔"; }`           |
| `::first-letter` | Styles first letter           | `p::first-letter { font-size: 200%; }` |
| `::first-line`   | Styles first line             | `p::first-line { color: red; }`        |
| `::selection`    | Styles selected text          | `::selection { background: yellow; }`  |

---

## 🔹 6. **Logical (Level 4) Pseudo-classes** *(Newer CSS)*

| Selector        | Description                              |
| --------------- | ---------------------------------------- |
| `:is()`         | Matches any selector inside it           |
| `:where()`      | Like `:is()`, but with **0 specificity** |
| `:has()`        | Selects elements that contain children   |
| `:dir(ltr/rtl)` | Matches text direction                   |
| `:lang(en)`     | Matches language                         |

```css
:is(h1, h2, h3) {
  font-weight: bold;
}

article:has(img) {
  border: 1px solid #ccc;
}
```

---

## 🎯 Special Selectors

| Selector        | Description                  |
| --------------- | ---------------------------- |
| `*`             | Universal selector           |
| `html`, `body`  | Root-level elements          |
| `:root`         | Matches the document root    |
| `::marker`      | Bullet/number of a list item |
| `::placeholder` | Placeholder text in input    |

---

## ✅ Summary

* Use `.` for class, `#` for ID, and `tag` for elements
* Combine selectors to make powerful targeting rules
* Use `:hover`, `:nth-child()`, and `::before` for interactivity and layout
* Modern CSS adds `:is()`, `:has()`, and more for flexibility

---

