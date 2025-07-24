## ✅ **What is `event.preventDefault()`?**

`event.preventDefault()` is a method used in JavaScript to **stop the browser's default behavior** for a given event.

---

## 🧪 Example 1: Prevent form from reloading the page

### 🔻 HTML:

```html
<form onsubmit="handleSubmit(event)">
  <input type="text" placeholder="Type something" />
  <button type="submit">Submit</button>
</form>
```

### 🟨 JavaScript:

```js
function handleSubmit(event) {
  event.preventDefault(); // 🔥 Stops form from reloading the page
  console.log("Form submitted with JS logic instead!");
}
```

---

### 🧠 What would happen **without** `preventDefault()`?

* Clicking "Submit" would cause the page to reload (form tries to send data via HTTP POST).
* You’d lose all your JavaScript state or dynamic page logic.

---

## 🧪 Example 2: Prevent link from navigating

```html
<a href="https://google.com" onclick="event.preventDefault()">Click me</a>
```

* Normally, clicking this would take you to Google.
* But `event.preventDefault()` stops the navigation.

---

## 📚 Syntax:

```js
element.addEventListener("click", function(event) {
  event.preventDefault();
});
```

---

## 🎯 Common Use Cases

| Scenario           | Why use `preventDefault()`?    |
| ------------------ | ------------------------------ |
| Form submission    | Prevents reloading page        |
| Anchor links       | Prevents navigation            |
| Drag & Drop        | Stops default browser behavior |
| Right-click        | Prevent default context menu   |
| Keyboard shortcuts | Stop unwanted scrolling, etc.  |

---

## 🔧 Bonus: `preventDefault()` vs `stopPropagation()`

* `preventDefault()` → stops **browser’s default action**
* `stopPropagation()` → stops **event from bubbling up** to parent elements

```js
event.preventDefault();   // stops default (e.g., navigation)
event.stopPropagation();  // stops bubbling to parent listeners
```

---

## ✅ Summary

| Method              | Effect                                 |
| ------------------- | -------------------------------------- |
| `preventDefault()`  | Stops the browser's default behavior   |
| `stopPropagation()` | Stops event from reaching parent nodes |

---

