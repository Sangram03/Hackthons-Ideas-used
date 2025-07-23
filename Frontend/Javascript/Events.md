### 📣 What Are Events in JavaScript?

**Events** in JavaScript are **signals** that something has happened in the **browser** — like a user clicking a button, pressing a key, or loading a page. You can **listen for** and **respond to** these events using **event handlers**.

---

## 🔔 Examples of Common Events

| Event       | Triggered When...                |
| ----------- | -------------------------------- |
| `click`     | User clicks an element           |
| `mouseover` | Mouse hovers over an element     |
| `mouseout`  | Mouse leaves an element          |
| `keydown`   | Key is pressed                   |
| `keyup`     | Key is released                  |
| `submit`    | A form is submitted              |
| `change`    | Input or select value is changed |
| `load`      | Page or image finishes loading   |
| `scroll`    | User scrolls the page or element |

---

## ✅ Basic Syntax for Adding Events

### 1. **Using HTML attribute:**

```html
<button onclick="sayHello()">Click Me</button>
```

### 2. **Using JavaScript inline:**

```javascript
document.getElementById("btn").onclick = function () {
  alert("Button clicked!");
};
```

### 3. **Using `addEventListener` (recommended):**

```javascript
document.getElementById("btn").addEventListener("click", () => {
  alert("Clicked via addEventListener!");
});
```

---

## 🧠 Why `addEventListener` is better?

* You can add **multiple listeners** to the same element.
* It's more **flexible** and **modern**.
* Better **separation of concerns** (HTML and JS are separate).

---

## 📦 Example: Button Click

### HTML:

```html
<button id="myBtn">Click Me</button>
```

### JavaScript:

```javascript
document.getElementById("myBtn").addEventListener("click", () => {
  console.log("Button was clicked!");
});
```

---

## 🧩 Event Object

When an event occurs, JavaScript passes an **event object** to your function:

```javascript
document.addEventListener("click", function (event) {
  console.log(event.type);       // "click"
  console.log(event.target);     // the clicked element
});
```

---

## 🔁 Event Types and Examples

### 🔘 `click`

```javascript
button.addEventListener("click", () => {
  console.log("Button clicked");
});
```

### ⌨️ `keydown` and `keyup`

```javascript
document.addEventListener("keydown", (e) => {
  console.log("You pressed:", e.key);
});
```

### 📝 `input` / `change`

```javascript
input.addEventListener("input", (e) => {
  console.log("Current value:", e.target.value);
});
```

### 🧾 `submit` (for forms)

```javascript
form.addEventListener("submit", (e) => {
  e.preventDefault(); // prevent page reload
  console.log("Form submitted");
});
```

---

## 🚦 Event Propagation: Bubbling and Capturing

* **Bubbling**: Event goes from **child → parent**.
* **Capturing**: Event goes from **parent → child** (less common).

```javascript
element.addEventListener("click", handler, true); // capturing
element.addEventListener("click", handler, false); // bubbling (default)
```

---

## 🧨 Remove Event Listener

```javascript
const handler = () => console.log("clicked!");
button.addEventListener("click", handler);

// Later:
button.removeEventListener("click", handler);
```

---

## ✅ Summary

* **Events** let you respond to user interaction and browser behavior.
* Use **`addEventListener`** for modern, flexible handling.
* You can **access details** about the event via the `event` object.
* Understand **bubbling and capturing** for advanced use.

---

