## 🔹 What is Mo.js?

* **Official site:** [https://mojs.github.io](https://mojs.github.io)
* **Core idea:** Create smooth and beautiful animations with simple, modular code.
* **Focus:** Burst effects, shape animations, timeline sequencing, and motion paths.
* **Works with:** HTML elements, SVGs, and JavaScript objects.
* **Written in:** Vanilla JavaScript (no dependencies)

---

## 🔸 Installation

### Option 1: CDN

```html
<script src="https://cdn.jsdelivr.net/npm/@mojs/core"></script>
```

### Option 2: npm

```bash
npm install @mojs/core
```

---

## 🔹 Mo.js Key Concepts

Mo.js uses **shape objects**, **tweens**, and **timelines**.

### ✅ Shape animations:

```js
import mojs from '@mojs/core';

const circle = new mojs.Shape({
  shape: 'circle',
  radius: 50,
  fill: 'deeppink',
  duration: 2000,
  repeat: 999,
  yoyo: true
}).play();
```

* `shape`: `circle`, `rect`, `polygon`, `line`, etc.
* `duration`: how long animation runs
* `repeat`: how many times to repeat (`999` = infinite)
* `yoyo`: reverse after each repeat

---

### ✅ Burst animation (like fireworks/explosions)

```js
const burst = new mojs.Burst({
  left: 0, top: 0,
  radius: { 0: 100 },
  count: 10,
  children: {
    shape: 'circle',
    radius: 20,
    fill: 'yellow',
    stroke: 'black',
    strokeWidth: 2,
    duration: 2000
  }
});

document.addEventListener('click', function (e) {
  burst.tune({ x: e.pageX, y: e.pageY }).replay();
});
```

💥 A beautiful burst animation wherever the user clicks.

---

### ✅ Timeline (for sequencing animations)

```js
const circle = new mojs.Shape({ ... });
const rect = new mojs.Shape({ shape: 'rect', ... });

const timeline = new mojs.Timeline();

timeline.add(circle, rect);
timeline.play();
```

🔁 Timeline allows you to sync multiple animations and control them together.

---

## 🔸 Mo.js Animation Properties

| Property                              | Description                         |
| ------------------------------------- | ----------------------------------- |
| `duration`                            | Total time of animation             |
| `delay`                               | Delay before animation starts       |
| `repeat`                              | Number of times animation repeats   |
| `yoyo`                                | Reverses animation each repeat      |
| `easing`                              | Animation easing style (`'sin.in'`) |
| `scale`, `x`, `y`, `opacity`, `angle` | Transformation props                |
| `tween`                               | Used to animate JavaScript values   |

---

## 🔹 Example: Animate DOM Element

```js
const htmlTween = new mojs.Html({
  el: '#myDiv',
  x: { 0: 100 },
  opacity: { 1: 0 },
  duration: 1000
});

htmlTween.play();
```

---

## 🔸 Supported Shapes

* `circle`
* `rect`
* `polygon`
* `line`
* `cross`
* `equal`
* `zigzag`
* `curve`
* `heart` 💖

Each shape supports stroke, fill, strokeWidth, angle, etc.

---

## 🔹 Custom Easing

Mo.js allows you to use advanced or custom easing:

```js
easing: 'cubic.out' // prebuilt
```

Or:

```js
easing: mojs.easing.path('M0,100 C20,0 80,0 100,100') // custom curve
```

---

## 🔸 Mo.js Use Cases

✅ Button click effects
✅ Celebration bursts (like confetti, fireworks)
✅ SVG shape morphing
✅ Custom loaders
✅ Interactive motion paths
✅ UI feedback (hover, focus)

---

## 🔹 Comparison: Mo.js vs Others

| Feature       | Mo.js         | GSAP       | Anime.js | Lottie             |
| ------------- | ------------- | ---------- | -------- | ------------------ |
| File Size     | \~20KB        | \~50KB+    | \~14KB   | Medium (uses JSON) |
| Timeline      | ✅ Built-in    | ✅ Advanced | ✅        | ❌                  |
| Physics-based | ❌             | ✅ (plugin) | ❌        | ❌                  |
| SVG/Shapes    | ✅ Very strong | ✅          | ✅        | ✅ (via AE)         |
| Interactivity | ✅ Click/hover | ✅          | ✅        | Limited            |
| React Support | Manual        | ✅          | ✅        | ✅ via wrapper      |

---

## 🔸 Resources

* 🛠️ [Playground](https://mojs.github.io/playground/)
* 📘 [Documentation](https://mojs.github.io/api/)
* 🎨 [Shape Editor Tool](https://mojs.github.io/tools/)

---

## 🔹 Quick Recap

* 🎨 **Creative** animations (not just UI transitions)
* 🧩 Modular structure (tweens, bursts, shapes, timeline)
* 🚀 Easy to use and powerful for custom effects
* 💡 Great for **eye-catching animations** on buttons, clicks, page transitions

---

