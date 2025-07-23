## 🔷 Full Code First

```tsx
const Carousel: React.FC<CarouselProps> = ({ items, autoPlayInterval = 5000 }) => {
  const [currentIndex, setCurrentIndex] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setCurrentIndex((current) => (current + 1) % items.length);
    }, autoPlayInterval);

    return () => clearInterval(interval);
  }, [items.length, autoPlayInterval]);

  const prev = () => {
    setCurrentIndex((current) => (current - 1 + items.length) % items.length);
  };

  const next = () => {
    setCurrentIndex((current) => (current + 1) % items.length);
  };
```

---

## ✅ Line-by-Line Breakdown

### 1. `const Carousel: React.FC<CarouselProps> = (...)`

* This is a **typed functional component** using TypeScript.
* `CarouselProps` is the interface that defines the props.
* `React.FC` means it's a **React Functional Component**.

### 2. `({ items, autoPlayInterval = 5000 })`

* `items`: Required prop – an array of elements to show as slides.
* `autoPlayInterval = 5000`: Optional prop with **default value** (5000 ms or 5 seconds).

---

### 3. `const [currentIndex, setCurrentIndex] = useState(0);`

* This uses `useState` to **track the index** of the currently visible slide.
* Initially, it shows slide at index `0`.

---

### 4. `useEffect(() => { ... }, [items.length, autoPlayInterval]);`

This hook runs after the component mounts and whenever `items.length` or `autoPlayInterval` changes.

#### Inside:

```ts
const interval = setInterval(() => {
  setCurrentIndex((current) => (current + 1) % items.length);
}, autoPlayInterval);
```

* Sets up an **interval** that runs every `autoPlayInterval` milliseconds.
* Increments the `currentIndex` cyclically:

  * `(current + 1) % items.length` → wraps around when it reaches the end.

#### Cleanup:

```ts
return () => clearInterval(interval);
```

* This clears the old interval when the component unmounts or the dependencies change.

✅ **Why?** To prevent **multiple intervals** or memory leaks.

---

### 5. `const prev = () => { ... }`

```ts
setCurrentIndex((current) => (current - 1 + items.length) % items.length);
```

* Decreases the index (moves to **previous slide**).
* Adds `items.length` before modulo to avoid **negative indexes**.
* `% items.length` wraps to the last slide when at index `0`.

---

### 6. `const next = () => { ... }`

```ts
setCurrentIndex((current) => (current + 1) % items.length);
```

* Increases the index (moves to **next slide**).
* `% items.length` makes it loop back to `0` after the last slide.

---

## 🎯 Final Use Case Example

```tsx
<Carousel items={[
  <div>Slide 1</div>,
  <div>Slide 2</div>,
  <div>Slide 3</div>,
]} autoPlayInterval={3000} />
```

---

## ✅ Summary

| Feature             | Explanation                                        |
| ------------------- | -------------------------------------------------- |
| `useState`          | Tracks the current slide index                     |
| `useEffect`         | Automatically advances the slide every few seconds |
| `prev()` & `next()` | Manual navigation between slides                   |
| `% items.length`    | Makes the carousel loop (circular)                 |

---

