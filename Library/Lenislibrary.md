**Lenis** is a modern **smooth scroll library** for web development, primarily used in JavaScript-based front-end projects. It provides buttery-smooth scrolling with customizable effects and is especially useful for enhancing user experience in visually-rich or interactive websites.

---

## 🔍 What is Lenis?

Lenis is a **lightweight JavaScript library** built for **smooth and customizable scroll animations**. Developed by **Studio Freight**, it replaces the native browser scroll with a custom one, enabling:

* consistent behavior across all browsers
* frame-synced scroll events
* advanced control over scroll velocity, easing, and behavior

> 🔗 Official site: [https://lenis.studiofreight.com/](https://lenis.studiofreight.com/)
> 🔗 GitHub: [https://github.com/studio-freight/lenis](https://github.com/studio-freight/lenis)

---

## ✅ Key Features

* **Smooth scrolling**: Uses `requestAnimationFrame` to create fluid motion.
* **Scroll normalization**: Same scroll feel across devices and browsers.
* **Scroll control**: Easily pause, start, stop scroll programmatically.
* **GSAP integration**: Compatible with GSAP and other animation libraries.
* **Supports scroll triggers**: Useful for scroll-based effects or animations.

---

## 📦 Installation

Install via npm:

```bash
npm install @studio-freight/lenis
```

Or use a CDN:

```html
<script src="https://unpkg.com/@studio-freight/lenis"></script>
```

---

## 🧠 Basic Usage Example (JavaScript)

```js
import Lenis from '@studio-freight/lenis'

const lenis = new Lenis()

function raf(time) {
  lenis.raf(time)
  requestAnimationFrame(raf)
}

requestAnimationFrame(raf)
```

> You typically wrap your scroll animations inside `raf()` (request animation frame) to ensure they’re synced with Lenis’s scrolling.

---

## 🛠️ Use Cases

### 1. **Creative Websites & Portfolios**

* Great for designers, artists, and agencies wanting a premium feel.
* Adds fluid scroll that feels better than default browser scroll.

### 2. **Scroll-triggered Animations**

* Works seamlessly with libraries like **GSAP ScrollTrigger**.
* Smooth scrolling helps prevent jittery or misaligned triggers.

### 3. **Parallax Effects**

* Lenis makes parallax smoother and more predictable.

### 4. **Controlling Scroll Behavior**

* Temporarily disable scroll (e.g., during modals).
* Add scroll to elements, not just the window (custom containers).

---

## 💡 Code with GSAP ScrollTrigger Example

```js
import Lenis from '@studio-freight/lenis'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const lenis = new Lenis()

lenis.on('scroll', ScrollTrigger.update)

gsap.ticker.add((time) => {
  lenis.raf(time * 1000)
})
```

---

## ⚠️ Things to Keep in Mind

* Lenis **replaces native scroll**, so some default browser behaviors (like anchor links) may need special handling.
* Ensure layout compatibility if your website uses full-page sections or sticky headers.
* If using with frameworks (e.g., React, Next.js, Vue), consider wrapping it inside `useEffect` or lifecycle methods.

---

## 📚 Summary

| Feature           | Description                              |
| ----------------- | ---------------------------------------- |
| Type              | Smooth scroll library                    |
| Developed by      | Studio Freight                           |
| Use in            | Creative web projects, animations        |
| Framework support | Works in vanilla JS, React, Next.js, Vue |
| Scroll control    | Yes (start, stop, pause, resume)         |
| Parallax + GSAP   | Fully compatible                         |

---
