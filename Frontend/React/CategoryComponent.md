```jsx
<CategoryComponent category={category} />
```

Here you're **passing a prop named `category`** to a React component called `CategoryComponent`.

---

## 🧠 What Is `category={category}`?

This is a **prop assignment**.

* The **left side** (`category`) is the **name of the prop** you're passing to a component.
* The **right side** (`category`) is the **variable** or **value** you're passing in.

So this line is saying:
➡️ "Hey `CategoryComponent`, here’s a prop called `category`, and its value is whatever is in the variable `category`."

---

## 🧾 Example in Context

### ✅ Parent Component

```jsx
const Home = () => {
  const category = "Fruits";

  return (
    <CategoryComponent category={category} />
  );
};
```

### ✅ Child Component

```jsx
const CategoryComponent = ({ category }) => {
  return (
    <h2>Selected Category: {category}</h2>
  );
};
```

🟢 Output:

```
Selected Category: Fruits
```

---

## 🔄 Destructuring in the Child

You could also access it like this:

### Option 1: With props object

```js
const CategoryComponent = (props) => {
  return <div>{props.category}</div>;
};
```

### Option 2: Destructuring directly

```js
const CategoryComponent = ({ category }) => {
  return <div>{category}</div>;
};
```

✅ **Cleaner and preferred** when you need just specific props.

---

## 🧪 Dynamic Example

```jsx
const App = () => {
  const categories = ["Fruits", "Vegetables", "Dairy"];

  return (
    <div>
      {categories.map((cat, index) => (
        <CategoryComponent key={index} category={cat} />
      ))}
    </div>
  );
};

const CategoryComponent = ({ category }) => {
  return <p>📦 {category}</p>;
};
```

🟢 Output:

```
📦 Fruits
📦 Vegetables
📦 Dairy
```

---

## ⚡ Summary

| Syntax                | Meaning                                                                         |
| --------------------- | ------------------------------------------------------------------------------- |
| `category={category}` | Passing a prop named `category` with the value of the local variable `category` |
| In component          | Access via `props.category` or destructure: `({ category })`                    |
| Purpose               | Used to **share data** from parent to child components                          |

---

