```js
const foodSchema = new mongoose.Schema({
    name: { type: String, require: true },
    description: { type: String, require: true },
    price: { type: Number, require: true },
    image: { type: String, require: true },
    category: { type: String, require: true },
});
```

---

## 🔍 Detailed Explanation

Each field (`name`, `description`, etc.) has options like `type`, `require`, and optionally `unique`. Let’s understand each:

---

## 1. ✅ `type`

### 👉 What it means:

Specifies the **data type** of the field.

### Common types:

| Type       | Meaning                         |
| ---------- | ------------------------------- |
| `String`   | Text value (e.g., "Pizza")      |
| `Number`   | Numeric value (e.g., 99.99)     |
| `Boolean`  | true or false                   |
| `Date`     | Date object                     |
| `Array`    | List of values                  |
| `ObjectId` | Used to reference another model |

### ✅ Example:

```js
name: { type: String }
price: { type: Number }
```

---

## 2. ✅ `required` (`require` is a typo)

### 👉 What it means:

* Makes the field **mandatory**.
* If not provided, MongoDB will throw a validation error when saving.

### Correct usage:

```js
name: { type: String, required: true }
```

### ⚠️ Note:

In your code, you wrote `require: true`, but it should be:

```js
required: true  ✅
```

---

## 3. ✅ `unique`

### 👉 What it means:

* Ensures **no two documents** have the same value for this field.
* Useful for fields like email, username, or ID.

### ✅ Example:

```js
email: { type: String, required: true, unique: true }
```

### ⚠️ Note:

`unique` is **not a validator**, it creates a **unique index** in the database.

---

## ✅ Final Clean Schema with Fixes

```js
import mongoose from "mongoose";

const foodSchema = new mongoose.Schema({
  name: { type: String, required: true },         // Name is a required string
  description: { type: String, required: true },  // Description is required
  price: { type: Number, required: true },        // Price must be a number
  image: { type: String, required: true },        // Image URL is required
  category: { type: String, required: true },     // Category name is required
});

const foodModel = mongoose.models.food || mongoose.model("food", foodSchema);

export default foodModel;
```

---

## 🧠 Bonus: Add `unique` Example

If you want to make sure no two food items have the same name:

```js
name: { type: String, required: true, unique: true }
```

---

## 🧪 Usage Example

```js
const newFood = new foodModel({
  name: "Veg Burger",
  description: "Tasty veg burger with lettuce",
  price: 99,
  image: "http://example.com/image.jpg",
  category: "Fast Food"
});

await newFood.save(); // Will throw error if required field is missing
```

---

## 🔚 Summary Table

| Field Option | Meaning                                           |
| ------------ | ------------------------------------------------- |
| `type`       | Data type (String, Number, etc.)                  |
| `required`   | Makes the field mandatory                         |
| `unique`     | Ensures values are not repeated (creates index)   |
| `default`    | Sets default value if none is provided (optional) |

---

