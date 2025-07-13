## ✅ Step 1: Install GSAP

If you haven’t already, install GSAP using npm or yarn:

```bash
npm install gsap
```

or

```bash
yarn add gsap
```

---

## ✅ Step 2: Basic Usage in a React Component

Here’s a simple example animating a `<div>` when the component loads:

### 🔸 **Example: Move box 200px to the right on mount**

```jsx
import React, { useEffect, useRef } from "react";
import { gsap } from "gsap";

const Box = () => {
  const boxRef = useRef(null);

  useEffect(() => {
    gsap.to(boxRef.current, {
      x: 200,
      duration: 1.5,
      ease: "power2.out",
    });
  }, []);

  return (
    <div
      ref={boxRef}
      style={{
        width: 100,
        height: 100,
        backgroundColor: "red",
        margin: "100px auto",
      }}
    >
      {/* Animated Box */}
    </div>
  );
};

export default Box;
```

---

## ✅ Step 3: Common GSAP Animation Options

| Property   | Description                    |
| ---------- | ------------------------------ |
| `x`, `y`   | Translate position             |
| `rotation` | Rotate in degrees              |
| `scale`    | Scale up/down                  |
| `opacity`  | Fade in/out                    |
| `duration` | Time in seconds                |
| `delay`    | Wait before starting animation |
| `ease`     | Animation easing type          |

---

## ✅ Step 4: Timeline Example (Sequenced Animations)

```jsx
import React, { useEffect, useRef } from "react";
import { gsap } from "gsap";

const TimelineExample = () => {
  const box1 = useRef(null);
  const box2 = useRef(null);

  useEffect(() => {
    const tl = gsap.timeline({ defaults: { duration: 1 } });

    tl.to(box1.current, { x: 150 })
      .to(box2.current, { y: 100, backgroundColor: "blue" });
  }, []);

  return (
    <div>
      <div ref={box1} style={{ width: 100, height: 100, background: "red", margin: 10 }} />
      <div ref={box2} style={{ width: 100, height: 100, background: "green", margin: 10 }} />
    </div>
  );
};

export default TimelineExample;
```

---

## ✅ Step 5: ScrollTrigger (Optional Plugin)

If you want animations to trigger on scroll:

```bash
npm install gsap@npm:@gsap/shockingly --save
```

Then:

```js
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
```

---
