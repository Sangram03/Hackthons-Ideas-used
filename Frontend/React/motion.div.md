## 📦 What is `motion.div`?

```jsx
import { motion } from "framer-motion";

<motion.div animate={{ opacity: 1 }} initial={{ opacity: 0 }} />
```

* `motion.div` is a **wrapped version of a `<div>`** that supports animations and gestures.
* Framer Motion provides `motion` components for every standard HTML and SVG element:

  * `motion.div`, `motion.span`, `motion.button`, etc.

---

## 🔧 Basic Props in `motion.div`

| Prop         | Purpose                                          |
| ------------ | ------------------------------------------------ |
| `initial`    | The initial animation state (e.g. opacity, x, y) |
| `animate`    | The target animation state                       |
| `exit`       | Animation when the component leaves the DOM      |
| `transition` | Controls animation timing like duration, delay   |
| `whileHover` | Animates when user hovers                        |
| `whileTap`   | Animates on tap or click                         |

---

## ✅ Example 1: Fade In

```jsx
<motion.div
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ duration: 1 }}
>
  Hello, I'm animated!
</motion.div>
```

---

## ✅ Example 2: Slide In from Left

```jsx
<motion.div
  initial={{ x: -100, opacity: 0 }}
  animate={{ x: 0, opacity: 1 }}
  transition={{ type: "spring", stiffness: 50 }}
>
  Slide In Content
</motion.div>
```

---

## ✅ Example 3: Hover Animation

```jsx
<motion.div
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.95 }}
>
  Click or Hover Me
</motion.div>
```

---

## ✨ Optional: AnimatePresence (for exit animations)

Use with conditionally rendered components:

```jsx
import { AnimatePresence, motion } from "framer-motion";

<AnimatePresence>
  {show && (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
    >
      Fades in and out
    </motion.div>
  )}
</AnimatePresence>
```

---

## 🧠 Summary

| Concept                    | Explanation                             |
| -------------------------- | --------------------------------------- |
| `motion.div`               | A `div` with built-in animation support |
| `initial`                  | Starting animation state                |
| `animate`                  | Target animation state                  |
| `transition`               | Timing of animation                     |
| `whileHover`, `whileTap`   | Interactive animations                  |
| `exit` + `AnimatePresence` | Animates on unmount                     |

---

