## ✅ What is `FormData`?

`FormData` is a built-in browser API that helps you:

* Collect data from forms
* Append fields manually
* Send it using `fetch` or `axios` to a backend (like Node.js or Express)
* Support file uploads (`enctype="multipart/form-data"`)

---

## 🔧 Syntax

```js
const formData = new FormData();
formData.append("fieldName", value);
```

---

## 📦 Common Use Case in React

Let’s say you have a form with fields: `name`, `description`, `price`, `category`, and an `image`.

### 🧠 Example Code:

```jsx
const handleSubmit = async (e) => {
  e.preventDefault();

  const formData = new FormData();
  formData.append("name", data.name);
  formData.append("description", data.description);
  formData.append("price", Number(data.price));
  formData.append("category", data.category);
  formData.append("image", image); // image is a File object

  // Send to server
  await axios.post("/api/food/upload", formData, {
    headers: { "Content-Type": "multipart/form-data" },
  });
};
```

---

## 🧩 Why Use FormData?

| Use Case               | Why `FormData` is Useful              |
| ---------------------- | ------------------------------------- |
| File Upload            | Supports image, PDF, or video upload  |
| Dynamic form fields    | Easy to loop over and append fields   |
| Axios/fetch compatible | Works well with API requests          |
| Encoded for multipart  | Automatically sets up proper encoding |

---

## 🗃️ Accessing FormData from a `<form>`

If you’re using an actual HTML `<form>`:

```js
const formElement = document.querySelector("form");
const formData = new FormData(formElement);
```

In React, we usually **manually control inputs**, so we build `FormData` from `useState` values.

---

## 🔍 Viewing FormData Contents (for debugging)

```js
for (let [key, value] of formData.entries()) {
  console.log(`${key}: ${value}`);
}
```

---

## ⚠️ Important Notes

* When sending `FormData`, **DO NOT manually set `Content-Type` to `multipart/form-data`** — the browser sets it automatically with proper boundary.
* Always ensure your backend (Node.js, Express, etc.) uses `multer` or similar middleware to parse `multipart/form-data`.

---

## ✅ Summary

| Feature          | Description                                   |
| ---------------- | --------------------------------------------- |
| `FormData`       | API to store form field data, including files |
| `append()`       | Method to add data to the FormData object     |
| Use with `axios` | Easily used to send form data to backend      |
| Good for uploads | Handles file uploads and text together        |

---
