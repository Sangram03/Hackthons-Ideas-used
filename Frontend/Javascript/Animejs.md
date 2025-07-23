## 🎞️ What is Anime.js?

**Anime.js** is a **lightweight JavaScript animation library** that works with:

* **DOM elements**
* **CSS properties**
* **SVG attributes**
* **JavaScript objects**
* **HTML attributes**

> It's fast, simple, and powerful — perfect for web UI animations, loading effects, SVG motions, and interactive storytelling.

---

## 📦 How to Use Anime.js

### ✅ Step 1: Add Anime.js

#### Option 1: CDN (HTML)

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
```

#### Option 2: NPM (React/Vite/Webpack)

```bash
npm install animejs
```

Then in your file:

```js
import anime from 'animejs';
```

---

## 💥 Basic Example

```html
<div class="box"></div>

<style>
  .box {
    width: 100px;
    height: 100px;
    background: red;
  }
</style>

<script>
  anime({
    targets: '.box',
    translateX: 250,
    duration: 1000,
    easing: 'easeInOutQuad'
  });
</script>
```

> 🎯 The red box moves 250px to the right over 1 second.

---

## 🧠 Syntax Overview

```js
anime({
  targets: 'selector or object',
  propertyToAnimate: value,
  duration: 1000,
  delay: 0,
  easing: 'linear',
  loop: false,
  direction: 'alternate',
  autoplay: true,
  complete: () => console.log("Done!")
});
```

---

## 🧱 Animatable Properties

| Type       | Example                          |
| ---------- | -------------------------------- |
| CSS Props  | `opacity`, `width`, `translateX` |
| Attributes | `d`, `stroke-dashoffset`, `cx`   |
| SVG        | `transform`, `fill`, `path`      |
| JS Objects | `{value: 0}` → `{value: 100}`    |

---

## 🛠️ Common Usage Examples

### 🟢 Translate (Move)

```js
anime({
  targets: '.box',
  translateX: 300,
  duration: 1500,
  easing: 'easeOutExpo'
});
```

---

### 🔁 Looping and Alternate Direction

```js
anime({
  targets: '.circle',
  translateY: 100,
  duration: 1000,
  direction: 'alternate',
  loop: true
});
```

---

### 🎛️ Multiple Properties

```js
anime({
  targets: '.box',
  translateX: 250,
  rotate: '1turn',
  scale: 1.5,
  duration: 2000
});
```

---

### 🎯 Target Multiple Elements

```js
anime({
  targets: '.items div',
  translateX: 250,
  delay: anime.stagger(100), // 100ms delay between each
});
```

---

### 🔢 Animate JavaScript Values

```js
let obj = { value: 0 };

anime({
  targets: obj,
  value: 100,
  round: 1,
  easing: 'easeInOutQuad',
  update: () => {
    console.log(obj.value);
  }
});
```

---

## ✨ Easing Functions

* `'linear'`
* `'easeInOutQuad'`
* `'easeInElastic'`
* `'easeOutExpo'`
* Custom cubic bezier: `cubicBezier(.5, .05, .1, .3)`

[See easing preview](https://animejs.com/documentation/#easings)

---

## ⏱️ Timeline Example (Sequence Animations)

```js
const tl = anime.timeline({
  easing: 'easeOutExpo',
  duration: 750
});

tl
.add({ targets: '.box', translateX: 250 })
.add({ targets: '.box', translateY: 100 })
.add({ targets: '.box', rotate: 360 });
```

---

## 🔗 SVG Path Animation

```js
anime({
  targets: 'path',
  strokeDashoffset: [anime.setDashoffset, 0],
  duration: 2000,
  easing: 'easeInOutSine',
  direction: 'alternate',
  loop: true
});
```

---

## 🎮 Controls (Play, Pause, Restart)

```js
const animation = anime({
  targets: '.box',
  translateX: 250,
  autoplay: false
});

animation.play();
animation.pause();
animation.restart();
```

---

## 🧩 Integration with React (Optional Example)

```jsx
import React, { useEffect, useRef } from "react";
import anime from "animejs";

export default function AnimeBox() {
  const boxRef = useRef();

  useEffect(() => {
    anime({
      targets: boxRef.current,
      translateX: 250,
      duration: 1000,
      easing: "easeInOutSine",
    });
  }, []);

  return <div ref={boxRef} style={{ width: 100, height: 100, background: 'red' }} />;
}
```

---

## 🌟 Why Use Anime.js?

✅ Easy syntax
✅ Works with any JS framework
✅ Lightweight (\~15kb min+gzip)
✅ Chainable and timeline support
✅ Works with CSS, SVG, HTML, and JS objects

---

## 📘 Official Resources

* 🔗 [Anime.js Website](https://animejs.com/)
* 📚 [Documentation](https://animejs.com/documentation/)
* 🧪 [CodePen Demos](https://codepen.io/search/pens?q=anime.js)

---

