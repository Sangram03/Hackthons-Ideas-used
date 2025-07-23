### 🧾 What is `(props)` in React?

In React, **`props`** (short for **properties**) are a way to pass **data from parent components to child components**.

---

## ✅ Basic Concept

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Usage
<Welcome name="Sangram" />
```

In the above:

* The component `Welcome` **receives** an object called `props`.
* That object contains: `{ name: "Sangram" }`.
* So `props.name` equals `"Sangram"`.

---

## 🧪 What Does `(props)` Mean?

When you write:

```jsx
function Component(props) {
  // ...
}
```

It means:

* `props` is a regular JavaScript object.
* All attributes passed to the component are grouped inside this `props` object.

---

## 🔹 Example with Multiple Props

```jsx
function Card(props) {
  return (
    <div>
      <h2>{props.title}</h2>
      <p>{props.description}</p>
    </div>
  );
}

// Usage
<Card title="React" description="JavaScript Library for UI" />
```

Here:

```js
props = {
  title: "React",
  description: "JavaScript Library for UI"
}
```

---

## 🔍 Destructuring `props`

Instead of:

```jsx
function Card(props) {
  return <h2>{props.title}</h2>;
}
```

You can write:

```jsx
function Card({ title }) {
  return <h2>{title}</h2>;
}
```

This is called **destructuring** and makes the code cleaner.

---

## 🧠 Why Use Props?

* **Reusability**: One component can be used with different data.
* **Customizability**: Props allow parent components to configure children.

---

## 🚫 Props Are Read-Only

You **can’t modify** `props` inside the child component.

```js
props.title = "New Title"; // ❌ This will throw an error
```

---

## 📌 Summary

| Term          | Meaning                                       |
| ------------- | --------------------------------------------- |
| `props`       | An object that holds data passed to component |
| `props.name`  | Access the `name` value passed down           |
| Destructuring | `({ name })` is same as `props.name`          |
| Read-only     | You cannot change props inside a component    |

---

Let me know if you want to explore:

* How props differ from `state`
* Passing functions as props
* Conditional rendering with props
