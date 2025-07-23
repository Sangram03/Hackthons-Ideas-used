### 🔍 JavaScript Selectors – Selecting HTML Elements

In JavaScript, **selectors** are used to **select and access elements** in the HTML DOM (Document Object Model). Once selected, you can **read or change** their content, style, or behavior.

---

## ✅ Commonly Used Selectors

| Method                              | Description                                                         |
| ----------------------------------- | ------------------------------------------------------------------- |
| `document.getElementById()`         | Selects **one element** by its ID                                   |
| `document.getElementsByClassName()` | Selects **all elements** with a class name (returns HTMLCollection) |
| `document.getElementsByTagName()`   | Selects all elements with the given tag                             |
| `document.querySelector()`          | Selects **first** element matching a CSS selector                   |
| `document.querySelectorAll()`       | Selects **all** elements matching a CSS selector (NodeList)         |

---

## 🔧 Examples

### 1. `getElementById`

```html
<p id="greet">Hello</p>
```

```javascript
const greeting = document.getElementById("greet");
greeting.textContent = "Hi Sangram!";
```

---

### 2. `getElementsByClassName`

```html
<p class="note">Note 1</p>
<p class="note">Note 2</p>
```

```javascript
const notes = document.getElementsByClassName("note");
notes[0].style.color = "red";
```

---

### 3. `getElementsByTagName`

```html
<ul>
  <li>One</li>
  <li>Two</li>
</ul>
```

```javascript
const items = document.getElementsByTagName("li");
console.log(items.length); // 2
```

---

### 4. `querySelector` (modern, flexible)

```html
<div class="card" id="main-card">Content</div>
```

```javascript
const card = document.querySelector(".card"); // By class
const main = document.querySelector("#main-card"); // By ID
```

---

### 5. `querySelectorAll`

```html
<div class="box">A</div>
<div class="box">B</div>
```

```javascript
const boxes = document.querySelectorAll(".box");

boxes.forEach(box => {
  box.style.border = "1px solid blue";
});
```

---

## 🧠 `HTMLCollection` vs `NodeList`

| Feature      | `getElementsBy...` | `querySelectorAll` |
| ------------ | ------------------ | ------------------ |
| Return Type  | HTMLCollection     | NodeList           |
| Live Updates | ✅ Yes              | ❌ No               |
| Loop Support | ❌ No `.forEach()`  | ✅ Has `.forEach()` |

---

## 🔥 Advanced Selectors with `querySelector`

| Selector             | Description           |
| -------------------- | --------------------- |
| `.class`             | Class selector        |
| `#id`                | ID selector           |
| `tag`                | Tag selector          |
| `div > p`            | Direct child          |
| `ul li`              | Nested selector       |
| `input[type="text"]` | Attribute selector    |
| `.box:nth-child(2)`  | Pseudo-class selector |

```javascript
document.querySelector("input[type='email']").value = "user@example.com";
```

---

## ✅ Best Practices

* Use `querySelector` and `querySelectorAll` for flexibility and modern standards.
* Store selected elements in constants.
* Avoid overly complex selectors for readability.
* Always check if the element exists before accessing/modifying it.

---
