```js
window.addEventListener('scroll', handleScroll);
```

means you're **adding a scroll event listener** to the window. Let's break it down clearly.

---

## ✅ What is `window.addEventListener()`?

`addEventListener` is a JavaScript method that **listens for events** on an element (like clicks, scrolls, key presses, etc.).

---

### ✅ Syntax

```js
element.addEventListener(eventType, eventHandler, options);
```

| Parameter              | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| `eventType`            | The name of the event (e.g., `'click'`, `'scroll'`, `'keydown'`) |
| `eventHandler`         | The function that runs when the event occurs                     |
| `options` *(optional)* | Settings like `{ once: true }` or `{ passive: true }`            |

---

### 🔍 In Your Example

```js
window.addEventListener('scroll', handleScroll);
```

| Part           | Meaning                                                     |
| -------------- | ----------------------------------------------------------- |
| `window`       | The entire browser window                                   |
| `'scroll'`     | Listens for when the user scrolls (up or down)              |
| `handleScroll` | A function you define that runs every time a scroll happens |

---

### 🧠 Example Usage

```js
const handleScroll = () => {
  const y = window.scrollY;
  console.log("Scrolled Y:", y);
};

window.addEventListener('scroll', handleScroll);
```

This logs how far the user has scrolled **vertically** every time they scroll.

---

## 🧽 Cleaning Up (in React `useEffect`)

If you’re using this in React, always **clean up** the event listener to prevent memory leaks:

```js
useEffect(() => {
  const handleScroll = () => {
    console.log("User is scrolling");
  };

  window.addEventListener('scroll', handleScroll);

  return () => {
    window.removeEventListener('scroll', handleScroll);
  };
}, []);
```

---

## 💡 Use Cases

* Showing/hiding a navbar on scroll
* Lazy loading content
* Infinite scroll
* "Back to top" buttons
* Animating elements on scroll (e.g. using libraries like AOS or Framer Motion)

---

## 🧠 Summary

| Feature             | Explanation                                                           |
| ------------------- | --------------------------------------------------------------------- |
| `addEventListener`  | Attaches a function to run when an event occurs                       |
| `'scroll'`          | Triggered whenever the user scrolls the page                          |
| `handleScroll`      | Your function that handles the scroll event                           |
| `useEffect cleanup` | Important in React to remove the listener when the component unmounts |

---

