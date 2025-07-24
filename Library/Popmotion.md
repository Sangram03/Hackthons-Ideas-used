## 🔹 What is Popmotion?

* **Official site:** [https://popmotion.io](https://popmotion.io)
* **Size:** \~11KB (gzip)
* **Written in:** TypeScript
* **Animation types:** Spring, decay, keyframes, tween, physics-based motion
* **Usage:** Ideal for animating CSS properties, SVGs, or custom values

---

## 🔸 Installation

### With npm/yarn:

```bash
npm install popmotion
# or
yarn add popmotion
```

### With CDN:

```html
<script src="https://unpkg.com/popmotion/dist/popmotion.global.min.js"></script>
```

---

## 🔹 Core Animation Types

### 1. **tween()**

Smoothly transitions between two values over time.

```js
import { tween } from 'popmotion';

tween({
  from: 0,
  to: 100,
  duration: 1000,
  onUpdate: v => console.log(v),
});
```

---

### 2. **spring()**

Physics-based spring animation.

```js
import { spring } from 'popmotion';

spring({
  from: 0,
  to: 100,
  stiffness: 100,
  damping: 10,
  onUpdate: v => console.log(v),
});
```

---

### 3. **decay()**

Simulates motion with friction (like momentum after a swipe).

```js
import { decay } from 'popmotion';

decay({
  velocity: 300,
  onUpdate: v => console.log(v),
});
```

---

### 4. **keyframes()**

Define multiple steps of an animation (like CSS keyframes).

```js
import { keyframes } from 'popmotion';

keyframes({
  values: [0, 100, 50, 75],
  duration: 2000,
  onUpdate: v => console.log(v),
});
```

---

## 🔸 Animate DOM Elements (like opacity, transform, etc.)

```js
import { tween } from 'popmotion';

const box = document.querySelector('.box');

tween({
  from: 0,
  to: 1,
  duration: 1500,
  onUpdate: latest => {
    box.style.opacity = latest;
  }
});
```

---

## 🔹 Using `styler` (for smoother DOM updates)

```js
import { styler, spring, value } from 'popmotion';

const box = document.querySelector('.box');
const divStyler = styler(box);
const boxY = value(0, v => divStyler.set('y', v));

spring({
  from: 0,
  to: 300,
  stiffness: 200,
  damping: 20
}).start(boxY);
```

* `styler` makes it easier to animate DOM/SVG by abstracting style handling.

---

## 🔸 Combining Animations with `composite` or `chain`

```js
import { chain, tween, spring } from 'popmotion';

chain(
  tween({ from: 0, to: 100, duration: 500 }),
  spring({ from: 100, to: 0, stiffness: 100 })
).start(v => {
  console.log(v);
});
```

---

## 🔹 Gesture-Based Animations

Popmotion also supports animations based on user gestures like **drag**, **mouse position**, and **velocity**.

Example: Animate based on mouse movement:

```js
import { pointer, value } from 'popmotion';

const box = document.querySelector('.box');
const boxStyler = styler(box);
const posX = value(0, x => boxStyler.set('x', x));

pointer({ x: posX }).start();
```

---

## 🔸 Popmotion vs Other Animation Libraries

| Library           | Strengths                          | Use Case                        |
| ----------------- | ---------------------------------- | ------------------------------- |
| **Popmotion**     | Physics, gestures, low-level power | Web apps, precise animations    |
| **Framer Motion** | Declarative, React-friendly        | React UIs, modern apps          |
| **GSAP**          | Full-featured, timeline control    | Web games, complex interactions |
| **Anime.js**      | Simple timeline + SVG support      | SVG, charts, UI animations      |
| **ScrollReveal**  | On-scroll effects                  | Reveal UI on scroll             |

---

## 🔹 When to Use Popmotion

✅ You want custom, low-level control over motion
✅ You need physics-based animation (like springs or decay)
✅ You want to animate numeric values, CSS, or SVGs
✅ You’re working in plain JS or need to build on top of it (e.g., in React with Framer Motion)

---

## 🔸 Resources

* 📘 [Official Docs](https://popmotion.io/api/)
* 🔧 [CodeSandbox Demos](https://codesandbox.io/search?query=popmotion)
* 💡 [Framer Motion](https://www.framer.com/motion/) — built on top of Popmotion, easier to use in React

---

