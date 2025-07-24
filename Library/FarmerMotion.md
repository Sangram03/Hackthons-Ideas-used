## 🧩 What is Framer Motion?

**Framer Motion** is a **production-ready animation library** for React. It provides:

* Declarative animations
* Easy-to-use API
* Layout animations
* Shared layout transitions
* Drag gestures
* Scroll animations
* Complex orchestrations

> 🔗 Official Site: [https://www.framer.com/motion/](https://www.framer.com/motion/)

---

## 📦 Installation

```bash
npm install framer-motion
# or
yarn add framer-motion
```

---

## 🛠 Basic Usage

```jsx
import { motion } from "framer-motion";

function MyComponent() {
  return (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      transition={{ duration: 1 }}
    >
      Hello Framer Motion!
    </motion.div>
  );
}
```

| Prop         | Purpose                                                                   |
| ------------ | ------------------------------------------------------------------------- |
| `initial`    | Defines the starting state of the animation                               |
| `animate`    | Defines the end state (it animates from `initial` to `animate`)           |
| `exit`       | Used for exit animations (when component unmounts with `AnimatePresence`) |
| `transition` | Controls timing, duration, easing, delays etc.                            |

---

## 🎯 Common Features

### 1. **Variants** – Reusable Animation States

```jsx
const boxVariants = {
  hidden: { opacity: 0, scale: 0.8 },
  visible: { opacity: 1, scale: 1 },
};

<motion.div
  variants={boxVariants}
  initial="hidden"
  animate="visible"
  transition={{ duration: 0.5 }}
/>
```

---

### 2. **Hover, Tap, Drag, and Gesture Support**

```jsx
<motion.button
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.9 }}
  drag
  dragConstraints={{ left: 0, right: 300 }}
>
  Click Me
</motion.button>
```

---

### 3. **AnimatePresence** – For Animating Components On Mount/Unmount

```jsx
import { AnimatePresence, motion } from "framer-motion";

function MyComponent({ isVisible }) {
  return (
    <AnimatePresence>
      {isVisible && (
        <motion.div
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          exit={{ opacity: 0 }}
        >
          I appear and disappear!
        </motion.div>
      )}
    </AnimatePresence>
  );
}
```

---

### 4. **Layout Animations**

```jsx
<motion.div layout> {/* Automatically animates between layout changes */} </motion.div>
```

> Add `layout` prop to animate size, position, and layout-related changes smoothly.

---

### 5. **Scroll Animations (useScroll & useTransform)**

```jsx
import { useScroll, useTransform, motion } from "framer-motion";

const Component = () => {
  const { scrollYProgress } = useScroll();
  const scale = useTransform(scrollYProgress, [0, 1], [1, 2]);

  return <motion.div style={{ scale }}>Scroll to scale</motion.div>;
};
```

---

## 🎬 Animation Controls (useAnimation)

```jsx
import { useAnimation, motion } from "framer-motion";

const controls = useAnimation();

<button onClick={() => controls.start({ x: 100 })}>Animate</button>

<motion.div animate={controls} />
```

---

## ⚡ When to Use Framer Motion

✅ Great for:

* Page transitions
* Element fade/slide/scale animations
* Drag-and-drop interactions
* Animated modals, cards, sliders
* Interactive UIs (e.g., dashboards, portfolio sites)

---

## 🧠 Advanced Concepts (optional)

* **LayoutGroup**: For coordinating layout changes across multiple components.
* **Shared Layout Transitions**: Smooth animations between shared components.
* **useMotionValue** and **useTransform**: Reactively bind animation values to styles or behaviors.
* **Custom easing functions** for highly controlled transitions.

---

## 🧪 Example Playground

Try it here:
👉 [https://codesandbox.io/s/framer-motion-basic-1x5g5](https://codesandbox.io/s/framer-motion-basic-1x5g5)

---

## 📘 Learn More

* [Framer Motion Docs](https://www.framer.com/motion/)
* [Framer Motion GitHub](https://github.com/framer/motion)
* Tutorials on YouTube (e.g., `Fireship`, `The Net Ninja`, `PedroTech`)

---
