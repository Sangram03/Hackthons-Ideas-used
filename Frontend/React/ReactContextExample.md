```js
setData(data => ({ ...data, [name]: value }))
```

This line is a **React state update function**. It’s used when updating part of an **object** stored in `useState`, such as in a form.

---

## ✅ Context Example

Imagine this form state in a React component:

```js
const [data, setData] = useState({
  name: '',
  email: '',
  age: ''
});
```

Now you want to update just **one field** (like `name` or `email`) based on user input:

```js
<input name="email" onChange={handleChange} />
```

Your handler might look like this:

```js
const handleChange = (e) => {
  const { name, value } = e.target;
  setData(data => ({ ...data, [name]: value }));
};
```

---

## 🔍 Explanation of `setData(data => ({ ...data, [name]: value }))`

| Part            | What it Does                                            |
| --------------- | ------------------------------------------------------- |
| `data =>`       | A function that receives the **current state** (`data`) |
| `{ ...data }`   | Creates a **copy** of the current state object          |
| `[name]: value` | Dynamically sets a property on the copied object        |
| `setData(...)`  | Updates the state with the new object                   |

---

## 🧠 Why use this pattern?

* Because `useState` **overwrites** the entire object — you need to copy the old data first (`...data`) and only change one field.
* Using `[name]` lets you update any field dynamically (instead of writing separate functions for name, email, etc.).

---

### 🔁 Example in Action

If the input field has:

```js
<input name="email" value={data.email} onChange={handleChange} />
```

Then when the user types:

1. `e.target.name === "email"`
2. `e.target.value === "abc@example.com"`
3. `setData(data => ({ ...data, ["email"]: "abc@example.com" }))`
4. New state becomes:

```js
{
  name: '',
  email: 'abc@example.com',
  age: ''
}
```

---

## ✅ Summary

| Code                   | Meaning                                             |
| ---------------------- | --------------------------------------------------- |
| `setData(data => ...)` | Functional way to update state using previous value |
| `{...data}`            | Keeps all existing values                           |
| `[name]: value`        | Dynamically updates the changed field               |

---
