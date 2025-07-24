## 🔹 What is Lottie?

* **Created by:** Airbnb
* **Works on:** Web, iOS, Android, React Native, Flutter, etc.
* **Animation format:** JSON (exported using [Bodymovin](https://github.com/airbnb/lottie-web) plugin for Adobe After Effects)
* **Renderer:** Uses SVG, Canvas, or HTML for rendering in web environments.

---

## 🔸 Why Use Lottie?

* ✅ Small file sizes (much smaller than GIFs or videos)
* ✅ Vector-based (so animations are resolution-independent)
* ✅ Easily controllable via JavaScript (play, pause, loop, speed control)
* ✅ Cross-platform support
* ✅ Great for microinteractions (like buttons, loaders, success animations)

---

## 🔹 How Lottie Works (Web Example)

1. **Install Lottie-web**

   ```bash
   npm install lottie-web
   ```

2. **Add the animation container in HTML**

   ```html
   <div id="lottie-container" style="width: 300px; height: 300px;"></div>
   ```

3. **Import and load animation**

   ```javascript
   import lottie from 'lottie-web';

   lottie.loadAnimation({
     container: document.getElementById('lottie-container'), // the dom element
     renderer: 'svg',  // svg / canvas / html
     loop: true,
     autoplay: true,
     path: 'animation.json'  // path to the animation JSON file
   });
   ```

---

## 🔸 Lottie Controls

```js
const animation = lottie.loadAnimation({...});

// Play / Pause
animation.play();
animation.pause();

// Stop
animation.stop();

// Change speed
animation.setSpeed(2); // 2x speed

// Go to a specific frame
animation.goToAndStop(50, true);

// Loop options
animation.loop = false;
```

---

## 🔹 Lottie in React (with `lottie-react`)

Install:

```bash
npm install lottie-react
```

Usage:

```jsx
import Lottie from 'lottie-react';
import animationData from './your-animation.json';

const MyComponent = () => {
  return <Lottie animationData={animationData} loop={true} />;
};
```

---

## 🔸 Where to Get Lottie Animations

* [https://lottiefiles.com](https://lottiefiles.com) — largest collection of free Lottie animations

---

## 🔹 Lottie Use Cases

* Loaders / Spinners
* Success / Error Feedback
* Button hover effects
* Onboarding animations
* Empty states
* App walkthroughs

---

## 🔸 Lottie vs Alternatives

| Feature       | Lottie   | GIF        | CSS Animations | Videos    |
| ------------- | -------- | ---------- | -------------- | --------- |
| File size     | Small    | Medium     | Very Small     | Large     |
| Performance   | High     | Medium-Low | High           | Medium    |
| Customization | High     | None       | High           | Low       |
| Interactivity | Yes      | No         | Yes            | No        |
| Scalability   | Infinite | Pixelated  | Infinite       | Pixelated |

---

