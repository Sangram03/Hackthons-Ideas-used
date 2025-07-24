## 🔹 What is Typed.js?

* **Official Site:** [https://mattboldt.com/demos/typed-js](https://mattboldt.com/demos/typed-js/)
* **GitHub:** [https://github.com/mattboldt/typed.js](https://github.com/mattboldt/typed.js)
* **File Size:** \~5KB gzipped
* **Written in:** Vanilla JavaScript (no dependencies)

---

## 🔸 Key Features

✅ Auto-typing effect
✅ Smart backspacing
✅ Multiple strings
✅ Looping
✅ Typing delays and speeds
✅ HTML tag parsing
✅ Callback support

---

## 🔹 Installation

### CDN (Quick Start)

```html
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
```

### NPM

```bash
npm install typed.js
```

### Import in JS

```js
import Typed from 'typed.js';
```

---

## 🔸 Basic Usage Example

### HTML

```html
<span id="typed-output"></span>
```

### JavaScript

```js
var typed = new Typed('#typed-output', {
  strings: ['Web Developer.', 'Designer.', 'Creator.'],
  typeSpeed: 50,
  backSpeed: 30,
  loop: true
});
```

🖊️ This will type each string, erase it, and repeat.

---

## 🔹 Configuration Options

| Option           | Description                                 | Example              |                   |
| ---------------- | ------------------------------------------- | -------------------- | ----------------- |
| `strings`        | Array of strings to type                    | `['Text1', 'Text2']` |                   |
| `typeSpeed`      | Speed of typing (ms per character)          | `50`                 |                   |
| `backSpeed`      | Speed of backspacing                        | `25`                 |                   |
| `startDelay`     | Delay before typing starts                  | `500`                |                   |
| `backDelay`      | Delay before backspacing                    | `1000`               |                   |
| `loop`           | Loop the typing animation                   | `true` / `false`     |                   |
| `showCursor`     | Show blinking cursor                        | `true` / `false`     |                   |
| `cursorChar`     | Character for cursor                        | \`'                  | '`, `'\_'\`, etc. |
| `smartBackspace` | Only delete what's different in next string | `true`               |                   |
| `fadeOut`        | Fade out text before next string            | `true`               |                   |

---

## 🔸 Example: Type HTML Tags (like `<strong>`)

```js
var typed = new Typed('#typed-output', {
  strings: ['I am a <strong>Web Developer</strong>.'],
  typeSpeed: 50,
  backSpeed: 30,
  loop: false,
  contentType: 'html'
});
```

---

## 🔹 Typed.js in React

### Step 1: Install

```bash
npm install typed.js
```

### Step 2: Component

```jsx
import React, { useEffect, useRef } from 'react';
import Typed from 'typed.js';

const TypedComponent = () => {
  const el = useRef(null);
  const typed = useRef(null);

  useEffect(() => {
    typed.current = new Typed(el.current, {
      strings: ['React Developer.', 'Frontend Engineer.'],
      typeSpeed: 50,
      backSpeed: 25,
      loop: true
    });

    return () => typed.current.destroy();
  }, []);

  return <span ref={el} />;
};

export default TypedComponent;
```

---

## 🔸 Event Callbacks

Typed.js supports event hooks like:

```js
new Typed('#typed', {
  strings: ['Hello'],
  onComplete: () => console.log('Typing complete!'),
  onStringTyped: (pos) => console.log('Finished string at index:', pos)
});
```

---

## 🔹 Common Use Cases

✅ Hero sections on landing pages
✅ Text rotators (e.g., “I am a \[developer | designer | creator]”)
✅ Interactive chatbot or storytelling UI
✅ Page loaders or intros
✅ Terminal-like typing effect

---

## 🔸 Comparison: Typed.js vs Alternatives

| Library      | Description                 | Ideal For                                |
| ------------ | --------------------------- | ---------------------------------------- |
| **Typed.js** | Simple typewriter animation | Headers, rotating text                   |
| **TypeIt**   | Advanced typing logic       | Precise control                          |
| **anime.js** | General animation engine    | Custom typing simulations                |
| **GSAP**     | Advanced animation          | Entire UI animation, not typing-specific |

---

## 🔧 Troubleshooting

* ❗ If typing shows no output, ensure the target `element ID/class` exists in DOM.
* 💡 Call `.destroy()` if re-rendering in frameworks like React to avoid memory leaks.
* 🚫 Avoid using the same ID in multiple places.

---

## ✅ Summary

| Feature        | Supported        |
| -------------- | ---------------- |
| Typing         | ✅                |
| Deleting       | ✅                |
| HTML content   | ✅                |
| Looping        | ✅                |
| Cursor control | ✅                |
| React support  | ✅ (manual setup) |

