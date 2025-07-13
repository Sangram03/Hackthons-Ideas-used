To **install GSAP (GreenSock Animation Platform)** in your project, follow these steps based on your project type:

---

### ✅ **For a JavaScript/React/Vite/Node Project (Using npm)**

#### 1. Install via npm:

```bash
npm install gsap
```

#### 2. Import and use in your JS/React file:

```js
import { gsap } from "gsap";

gsap.to(".box", { rotation: 360, duration: 2 });
```

---

### ✅ **For a simple HTML file (via CDN)**

#### Add this `<script>` tag in your HTML `<head>` or before the closing `</body>`:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

<script>
  gsap.to(".box", { rotation: 360, duration: 2 });
</script>
```

---

### ✅ Example (React + GSAP)

```jsx
import React, { useEffect, useRef } from "react";
import { gsap } from "gsap";

const Box = () => {
  const boxRef = useRef(null);

  useEffect(() => {
    gsap.to(boxRef.current, { x: 200, duration: 1 });
  }, []);

  return <div ref={boxRef} className="box" style={{ width: 100, height: 100, background: 'red' }} />;
};

export default Box;
```

---

