## 🔹 What is ScrollReveal?

* **Official site:** [https://scrollrevealjs.org](https://scrollrevealjs.org)
* **Core use:** Animate elements on scroll (fade, slide, rotate, scale, etc.)
* **File size:** Lightweight (\~3KB gzipped)
* **Dependency-free** (no jQuery or extra libraries needed)
* **Easy to integrate** with plain HTML/JS or frameworks like React, Vue

---

## 🔸 Installation

### Using CDN (quick setup)

```html
<script src="https://unpkg.com/scrollreveal"></script>
```

### Or using npm

```bash
npm install scrollreveal
```

### Import in JavaScript

```js
import ScrollReveal from 'scrollreveal';
```

---

## 🔹 Basic Usage Example

```html
<div class="box">Scroll me in!</div>
```

```js
ScrollReveal().reveal('.box');
```

➡️ Now, when `.box` scrolls into view, it will fade in by default.

---

## 🔸 Customizing the Animation

```js
ScrollReveal().reveal('.box', {
  origin: 'left',     // 'top', 'right', 'bottom', 'left'
  distance: '100px',  // How far the element moves
  duration: 1000,     // Animation duration in ms
  delay: 200,         // Delay before reveal starts
  opacity: 0,         // Initial opacity
  easing: 'ease-in-out',
  scale: 0.9,         // Zoom in/out
  reset: false,       // If true, animation runs every time it enters view
});
```

---

## 🔹 Chaining Multiple Animations

```js
ScrollReveal().reveal('.heading', { delay: 100 });
ScrollReveal().reveal('.text', { delay: 300 });
ScrollReveal().reveal('.image', { delay: 500 });
```

➡️ Elements will reveal one after another as you scroll.

---

## 🔸 ScrollReveal in React

```bash
npm install scrollreveal
```

```jsx
import React, { useEffect } from 'react';
import ScrollReveal from 'scrollreveal';

const MyComponent = () => {
  useEffect(() => {
    ScrollReveal().reveal('.reveal', {
      duration: 1000,
      origin: 'bottom',
      distance: '50px',
    });
  }, []);

  return (
    <div className="reveal">
      <h1>Hello with ScrollReveal</h1>
    </div>
  );
};

export default MyComponent;
```

---

## 🔹 Common Options (Cheat Sheet)

| Option     | Description                          | Example           |
| ---------- | ------------------------------------ | ----------------- |
| `origin`   | Animation direction                  | `'top'`, `'left'` |
| `distance` | How far to move the element          | `'50px'`          |
| `duration` | Animation time in ms                 | `800`             |
| `delay`    | Time to wait before animation starts | `300`             |
| `opacity`  | Starting opacity (0 = invisible)     | `0`               |
| `scale`    | Starting scale (0.9 = shrink)        | `0.9`             |
| `reset`    | Run every time in view               | `true` / `false`  |
| `mobile`   | Enable/disable on mobile             | `true` / `false`  |

---

## 🔸 Example Styles + HTML

```html
<style>
  .box {
    background: #7b2cbf;
    color: white;
    padding: 40px;
    margin: 20px;
    font-size: 24px;
    border-radius: 12px;
  }
</style>

<div class="box">Box 1</div>
<div class="box">Box 2</div>
```

```js
ScrollReveal().reveal('.box', {
  origin: 'bottom',
  distance: '80px',
  duration: 1000,
  interval: 200 // Reveals one after the other
});
```

---

## 🔹 When to Use ScrollReveal

✅ For lightweight, smooth scroll-based animation
✅ When you want fine control without a complex animation engine
✅ For performance-sensitive websites
✅ For non-heavy 3D/interactive animations (use GSAP or Framer Motion for that)

---

## 🔸 Alternatives to ScrollReveal

| Library               | Description                                  |
| --------------------- | -------------------------------------------- |
| **AOS.js**            | Animate On Scroll Library (CSS based)        |
| **Framer Motion**     | Powerful for React animations                |
| **GSAP**              | GreenSock Animation Platform — very powerful |
| **Locomotive Scroll** | Scroll-based UX with inertia                 |

---

