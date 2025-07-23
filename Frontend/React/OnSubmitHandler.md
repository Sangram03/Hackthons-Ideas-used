### 📝 `onSubmitHandler` in React — In Detail

In React, `onSubmitHandler` (often named `handleSubmit` or `onSubmit`) is a **function** used to handle form submissions.

---

### ✅ Basic Flow:

1. A form element listens for the `onSubmit` event.
2. The handler function is triggered when the user clicks a submit button.
3. You can:

   * Prevent default page reload.
   * Collect form data.
   * Validate input.
   * Send data to a backend (via `fetch`, `axios`, etc.).

---

## 🧩 Basic Example

```jsx
import React, { useState } from 'react';

const App = () => {
  const [name, setName] = useState('');

  const onSubmitHandler = (e) => {
    e.preventDefault(); // prevent page reload
    console.log("Form Submitted:", name);
  };

  return (
    <form onSubmit={onSubmitHandler}>
      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
        placeholder="Enter your name"
      />
      <button type="submit">Submit</button>
    </form>
  );
};

export default App;
```

---

## 🧠 Key Concepts

### ✅ 1. `e.preventDefault()`

Prevents the form from reloading the page (browser default behavior).

### ✅ 2. Form Data Collection

Use `useState` or `useRef` to track values and access them in the handler.

### ✅ 3. `onSubmit` Event

Placed directly on the `<form>` element, not the button.

---

## 🧪 With Multiple Inputs

```jsx
const [formData, setFormData] = useState({ email: '', password: '' });

const onSubmitHandler = (e) => {
  e.preventDefault();
  console.log("Form Data:", formData);
};

<form onSubmit={onSubmitHandler}>
  <input
    name="email"
    value={formData.email}
    onChange={(e) =>
      setFormData({ ...formData, [e.target.name]: e.target.value })
    }
  />
  <input
    name="password"
    type="password"
    value={formData.password}
    onChange={(e) =>
      setFormData({ ...formData, [e.target.name]: e.target.value })
    }
  />
  <button type="submit">Login</button>
</form>
```

---

## 📦 Typical Use Cases

* Login forms
* Registration forms
* Contact forms
* Feedback forms
* Filtering/search forms

---

## 💡 Best Practices

* Validate user inputs before submission.
* Use `type="submit"` on the button.
* Use a proper schema (like with `Formik` or `Yup` for bigger forms).
* Reset form on success if needed: `setFormData({ email: '', password: '' })`.

---

