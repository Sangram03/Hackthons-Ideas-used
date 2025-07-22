## ✅ What is `e.target.value`?

In React (and JavaScript in general), when you interact with a form element like an `<input>`, a change triggers an **event** — specifically an **`onChange` event**.

* `e` stands for **event**.
* `e.target` is the **element** that triggered the event (like an `<input>` or `<textarea>`).
* `e.target.value` is the **current value** of that element.

---

### 🧪 Example

```jsx
function NameForm() {
  const [name, setName] = useState("");

  const handleChange = (e) => {
    setName(e.target.value);
  };

  return (
    <div>
      <input type="text" onChange={handleChange} />
      <p>Your name is: {name}</p>
    </div>
  );
}
```

### 🔍 How it works:

1. You type "Alex" into the input box.
2. The `onChange` event fires.
3. `e.target` refers to the `<input>`.
4. `e.target.value` is `"Alex"`.
5. `setName("Alex")` updates the state.
6. Component re-renders and shows `Your name is: Alex`.

---

## 🧠 Think of it like:

```js
<input value="some text" />
```

Typing changes the `value` property of the input. `e.target.value` grabs that new value so you can store or use it.

---

## 🔁 Another Common Use Case: Checkbox

```jsx
<input
  type="checkbox"
  checked={isChecked}
  onChange={(e) => setIsChecked(e.target.checked)}
/>
```

* `e.target.checked` is used instead of `e.target.value` for checkboxes.

---

## 💡 Summary Table

| Element Type              | What to use        |
| ------------------------- | ------------------ |
| `<input type="text">`     | `e.target.value`   |
| `<textarea>`              | `e.target.value`   |
| `<select>`                | `e.target.value`   |
| `<input type="checkbox">` | `e.target.checked` |
| `<input type="radio">`    | `e.target.value`   |

---

