### `JSON.stringify()` in JavaScript

`JSON.stringify()` is a built-in JavaScript method that **converts a JavaScript object or value into a JSON-formatted string**.

---

### 🔹 Syntax

```js
JSON.stringify(value, replacer, space)
```

* `value` → The object or value to convert.
* `replacer` *(optional)* → A function or array to control what values are included.
* `space` *(optional)* → Adds indentation, white space, and line breaks (for pretty formatting).

---

### ✅ Basic Example

```js
const user = {
  name: "Sangram",
  age: 25,
};

const jsonString = JSON.stringify(user);
console.log(jsonString);
// Output: '{"name":"Sangram","age":25}'
```

---

### 🔸 Why is it used in `await whook.verify(JSON.stringify(req.body))`?

In this context:

```js
await whook.verify(JSON.stringify(req.body))
```

* `req.body` is likely a JavaScript object received from an HTTP POST request (like from a payment provider webhook).
* Some systems (e.g., **Razorpay**, **Stripe**, **Clerk**, etc.) send data in **raw JSON** and require **verification using the exact raw string** they sent.
* `JSON.stringify()` is used to **convert the `req.body` back into the raw JSON string** so that it can be **verified for authenticity**.

👉 This is important because even a small formatting difference (like whitespace or missing quotes) will cause verification to fail.

---

### ⚠️ Warning

`JSON.stringify()` output **must match exactly** what the original webhook payload looked like. Sometimes, if the body is parsed before getting raw access (like using `express.json()`), verification will fail.

In such cases, use `req.rawBody` or middleware to store the raw body before parsing.

---

### 🧠 Summary

* `JSON.stringify()` turns JavaScript objects into JSON text.
* Used in webhook verification to ensure **exact string match**.
* Common in authentication, API communication, and storage.

