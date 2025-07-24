## 🔹 What is ScrollMagic?

* **Official Site:** [https://scrollmagic.io](https://scrollmagic.io)
* **Purpose:** Trigger animations and effects based on scroll position.
* **Core concept:** “Scenes” that monitor scroll events and link them to animations.
* **Dependencies:** Vanilla JS, but often used with **GSAP** (GreenSock Animation Platform) for advanced animations.

---

## 🔸 Key Features

✅ Trigger animations on scroll
✅ Pin elements (make them stick during scroll)
✅ Parallax scrolling effects
✅ Sync animations with scroll progress
✅ Works with GSAP, Velocity.js, Anime.js, etc.
✅ Debugging tools and indicators

---

## 🔹 Installation

### CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js"></script>
<!-- Optional GSAP plugin -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/plugins/animation.gsap.min.js"></script>
<!-- Optional debug -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/plugins/debug.addIndicators.min.js"></script>
```

### NPM

```bash
npm install scrollmagic
```

---

## 🔸 Basic Example: Fade in on Scroll

### HTML

```html
<div id="trigger"></div>
<div id="animate" class="box">Hello, ScrollMagic!</div>
```

### JavaScript

```js
const controller = new ScrollMagic.Controller();

const scene = new ScrollMagic.Scene({
  triggerElement: "#trigger",
  duration: 300
})
.setClassToggle("#animate", "fade-in")
.addTo(controller);
```

### CSS

```css
.box {
  opacity: 0;
  transition: opacity 1s ease;
}

.fade-in {
  opacity: 1;
}
```

---

## 🔹 Using GSAP with ScrollMagic

```js
const controller = new ScrollMagic.Controller();

const tween = gsap.from("#animate", {
  opacity: 0,
  y: 100,
  duration: 1
});

new ScrollMagic.Scene({
  triggerElement: "#trigger",
  duration: 400,
  triggerHook: 0.9
})
.setTween(tween)
.addIndicators() // shows start/end points in dev
.addTo(controller);
```

---

## 🔸 Pinning Elements (Sticky on Scroll)

```js
new ScrollMagic.Scene({
  triggerElement: "#trigger",
  triggerHook: 0,
  duration: 500
})
.setPin("#pinned-element")
.addTo(controller);
```

📌 This will keep `#pinned-element` fixed while scrolling through a 500px duration.

---

## 🔹 Scene Options Overview

| Option           | Description                                         |
| ---------------- | --------------------------------------------------- |
| `triggerElement` | Element that starts the scene                       |
| `triggerHook`    | Position on screen to trigger (0 = top, 1 = bottom) |
| `duration`       | How long the scene lasts (in px or percent)         |
| `offset`         | Start scene offset from the triggerElement          |
| `reverse`        | Whether scene should reverse when scrolling up      |

---

## 🔸 Example Use Cases

✅ Reveal elements on scroll
✅ Scroll-progress bars
✅ Parallax effects
✅ Step-by-step storytelling (like scrollytelling pages)
✅ Trigger GSAP/Anime.js timelines
✅ Sticky headers or sidebars

---

## 🔹 ScrollMagic + GSAP Timeline Example

```js
const timeline = gsap.timeline();
timeline
  .from(".box1", { x: -100, opacity: 0, duration: 1 })
  .from(".box2", { y: 100, opacity: 0, duration: 1 });

new ScrollMagic.Scene({
  triggerElement: "#trigger",
  duration: 500
})
.setTween(timeline)
.addIndicators()
.addTo(controller);
```

---

## 🔸 ScrollMagic Debugging

Use `addIndicators()` to visualize:

```js
scene.addIndicators({
  name: "My Scene",
  colorStart: "#0f0",
  colorEnd: "#f00"
});
```

🧪 This helps you see **where and when** your scroll triggers happen.

---

## 🔹 ScrollMagic Alternatives (and Why/When)

| Library                | Good For                            | Notes                                     |
| ---------------------- | ----------------------------------- | ----------------------------------------- |
| **GSAP ScrollTrigger** | Modern scroll-based animation       | Replaces ScrollMagic, better maintained   |
| **Locomotive Scroll**  | Smooth scroll + parallax            | More advanced UI behavior, mobile support |
| **AOS.js**             | Simple scroll animations            | CSS-class based only                      |
| **Framer Motion**      | React animations, scroll + gestures | Very React-specific                       |

✅ **Recommendation:** Use **GSAP's ScrollTrigger** if you're starting new — it's newer, more powerful, and better maintained.

---

## 🔸 Final Thoughts

**ScrollMagic is best used when you:**

* Want precise scroll-triggered control
* Prefer working with plain JavaScript or GSAP
* Need pinning/parallax/effect syncing based on scroll

---
