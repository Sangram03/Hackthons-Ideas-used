### 🌀 `motion.img` in Detail – From Framer Motion

In **Framer Motion** (a popular React animation library), `motion.img` is a **motion-enhanced version of the HTML `<img>` tag**. It allows you to apply powerful animations and transitions to images in a declarative way.

---

## ✅ Basic Syntax

```tsx
import { motion } from "framer-motion";

<motion.img
  src="/your-image.jpg"
  alt="example"
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ duration: 1 }}
/>
```

---

## 📌 Key Concepts

| Property     | Description                                                                  |
| ------------ | ---------------------------------------------------------------------------- |
| `initial`    | The **starting state** of the animation (e.g., before the component appears) |
| `animate`    | The **end state** or the animated target                                     |
| `whileHover` | The animation that runs when the user **hovers** over the image              |
| `whileTap`   | Animation when the image is **clicked or tapped**                            |
| `exit`       | Used with `AnimatePresence` when the component is **removed** from the DOM   |
| `transition` | Controls timing like `duration`, `delay`, `ease`                             |

---

## ✨ Example 1: Fade-in Image on Load

```tsx
<motion.img
  src="/hero.jpg"
  alt="Hero"
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ duration: 1.5 }}
/>
```

---

## ✨ Example 2: Zoom-in on Hover

```tsx
<motion.img
  src="/product.jpg"
  alt="Product"
  whileHover={{ scale: 1.1 }}
  transition={{ type: "spring", stiffness: 300 }}
/>
```

---

## ✨ Example 3: Combined Animation

```tsx
<motion.img
  src="/banner.png"
  alt="Banner"
  initial={{ opacity: 0, scale: 0.8 }}
  animate={{ opacity: 1, scale: 1 }}
  transition={{ duration: 0.8 }}
  whileHover={{ scale: 1.05 }}
/>
```

---

## 🧠 Tip: All `motion` components behave like their HTML counterparts but with animation powers.

That means:

* `motion.div` = `<div>` + animation
* `motion.img` = `<img>` + animation
* `motion.button`, `motion.span`, `motion.svg`, etc.

---

## 🛠 Use Case Examples

* Smoothly animate product or portfolio images.
* Add hover scaling for better UX.
* Create intro animations for hero sections.
* Animate carousels or sliders.

---

## 📦 How to Install Framer Motion

If you haven't yet:

```bash
npm install framer-motion
# or
yarn add framer-motion
```

---

