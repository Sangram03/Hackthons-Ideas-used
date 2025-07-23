## 🎯 What is GSAP?

**GSAP (GreenSock Animation Platform)** is a robust, high-performance JavaScript animation library used to animate:

* HTML elements
* CSS properties
* SVG
* Canvas
* JavaScript objects

> It's widely used in production-level web applications, creative websites, and complex UI animations.

---

## ✅ Why Use GSAP?

| Feature             | Benefit                                       |
| ------------------- | --------------------------------------------- |
| ⚡ Fast & Performant | Up to 20x faster than jQuery                  |
| 🧠 Intuitive Syntax | Easy to read and use                          |
| 🔁 Timeline Control | Seamless sequencing and control               |
| 🔄 Cross-browser    | Works consistently across all modern browsers |
| 🎨 Animate Anything | CSS, SVG, canvas, JS values                   |
| 💥 Plugins          | ScrollTrigger, Draggable, MorphSVG, etc.      |

---

## 📦 Installation

### CDN (for HTML)

```html
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
```

### NPM (for React, Vite, Webpack)

```bash
npm install gsap
```

Then:

```js
import gsap from 'gsap';
```

---

## 💡 Basic GSAP Syntax

```js
gsap.to(".box", {
  x: 300,
  duration: 1,
  ease: "power2.out"
});
```

This animates `.box` from its current position to `x: 300px` in 1 second using a smooth easing curve.

---

## 🧱 Core Methods

| Method            | Purpose                                 |
| ----------------- | --------------------------------------- |
| `gsap.to()`       | Animate from current → target values    |
| `gsap.from()`     | Animate from values → current           |
| `gsap.fromTo()`   | Define both from and to values          |
| `gsap.set()`      | Set property immediately (no animation) |
| `gsap.timeline()` | Create sequence of animations           |

---

## 🧪 Examples

### 1. Simple Movement

```js
gsap.to(".box", {
  x: 200,
  duration: 2,
});
```

### 2. From-to Animation

```js
gsap.fromTo(".box",
  { x: 0, opacity: 0 },
  { x: 300, opacity: 1, duration: 1.5 }
);
```

### 3. Timeline Example

```js
const tl = gsap.timeline({ repeat: -1, yoyo: true });

tl.to(".box", { x: 100, duration: 1 })
  .to(".box", { rotation: 360, duration: 1 }, "-=0.5")
  .to(".box", { scale: 1.5, duration: 1 });
```

---

## ⏱️ Easing Options

GSAP comes with powerful ease presets:

* `"linear"`
* `"power1.inOut"`
* `"bounce.out"`
* `"elastic.in(1, 0.3)"`
* `"expo.out"`

```js
gsap.to(".box", { x: 400, ease: "bounce.out", duration: 2 });
```

---

## 🔗 Animating Multiple Elements (Stagger)

```js
gsap.to(".item", {
  y: 100,
  duration: 1,
  stagger: 0.2 // adds delay between each element
});
```

---

## ✨ Scroll-Based Animation with ScrollTrigger

Install ScrollTrigger plugin:

```bash
npm install gsap@npm:@gsap/shockingly gsap@npm:@gsap/shockingly --save
```

```js
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

gsap.to(".box", {
  scrollTrigger: {
    trigger: ".box",
    start: "top 80%",
    end: "bottom 30%",
    scrub: true,
    markers: true
  },
  x: 400,
  rotation: 360
});
```

---

## 🧩 GSAP Plugins

| Plugin            | Use Case                        |
| ----------------- | ------------------------------- |
| **ScrollTrigger** | Scroll-based animations         |
| **Draggable**     | Make elements draggable         |
| **MorphSVG**      | Morph between SVG shapes        |
| **SplitText**     | Animate text letter by letter   |
| **Flip**          | Animate layout changes smoothly |

---

## 🧠 GSAP with React

```jsx
import { useEffect, useRef } from "react";
import gsap from "gsap";

export default function GsapBox() {
  const boxRef = useRef();

  useEffect(() => {
    gsap.to(boxRef.current, { x: 200, duration: 1 });
  }, []);

  return <div ref={boxRef} className="box" />;
}
```

---

## 💎 Advanced Tips

* Use `.add()` in timelines for full control
* Combine GSAP with `IntersectionObserver` for lazy animation
* Use `onComplete` callbacks for chaining logic
* Use `%` or `vh/vw` units for responsive animations

---

## 📚 Official Resources

* 🌐 [GSAP Website](https://greensock.com/gsap/)
* 📖 [GSAP Docs](https://greensock.com/docs/)
* 🎥 [GSAP Crash Course (YouTube)](https://www.youtube.com/watch?v=3Haz4V4YRxw)
* 🧪 [CodePen Playground](https://codepen.io/GreenSock)

---
