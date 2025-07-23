```js
formData.append("name", data.name)
formData.append("description", data.description)
formData.append("price", Number(data.price))
formData.append("category", data.category)
formData.append("image", image)
```

---

## ✅ What is `FormData`?

`FormData` is a built-in JavaScript class used to **construct key/value pairs** to simulate form submissions, especially when dealing with file uploads (`multipart/form-data` encoding).

It allows you to send both **text data** and **binary (file/image)** data to the backend.

```js
const formData = new FormData();
```

---

## 🔍 Line-by-Line Explanation

### `formData.append("name", data.name)`

* Appends the value of `data.name` to the form field `name`.
* Example: `"Veg Burger"`

---

### `formData.append("description", data.description)`

* Adds a field named `description` to the form.
* Example: `"Delicious veg burger with lettuce"`

---

### `formData.append("price", Number(data.price))`

* Ensures the `price` value is sent as a number (not a string).
* Converts string input like `"99"` into `99`.
* Backend may expect numeric type — so this is a **good practice**.

---

### `formData.append("category", data.category)`

* Adds a `category` field like `"Fast Food"` or `"Beverages"`.

---

### `formData.append("image", image)`

* Adds an image file (binary) to the form.
* `image` should be a `File` object (usually from `<input type="file" />`).
* This is how you upload images or files.

✅ Example:

```js
const image = event.target.files[0];
```

---

## 📦 Complete Example

```js
const handleSubmit = async () => {
  const formData = new FormData();

  formData.append("name", data.name);
  formData.append("description", data.description);
  formData.append("price", Number(data.price));
  formData.append("category", data.category);
  formData.append("image", image); // image is a File object

  try {
    const res = await axios.post("/api/foods", formData, {
      headers: {
        "Content-Type": "multipart/form-data"
      }
    });

    console.log("Upload success", res.data);
  } catch (err) {
    console.error("Upload failed", err);
  }
};
```

---

## 🧠 Why Use `FormData`?

| Use Case                                        | Benefit                        |
| ----------------------------------------------- | ------------------------------ |
| File upload (image, PDF, etc.)                  | Easily handles binary data     |
| Multipart data submission                       | Works with form fields + files |
| Required in `multipart/form-data` POST requests | Proper encoding                |

---

## 🧪 Backend Expectation

If you're using Express with `multer`, the backend would expect the data like this:

```js
router.post("/api/foods", upload.single("image"), (req, res) => {
  console.log(req.body); // name, description, price, category
  console.log(req.file); // image file info
});
```

---

## ✅ Summary

| Line                            | Meaning                                |
| ------------------------------- | -------------------------------------- |
| `formData.append("key", value)` | Adds data to the request               |
| Handles both text and files     | Good for file uploads                  |
| `Number(data.price)`            | Ensures price is numeric               |
| `image` is a File object        | Uploaded using `<input type="file" />` |

---

