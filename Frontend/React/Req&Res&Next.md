## 🧠 In Short:

| Keyword | Meaning             | Purpose                                              |
| ------- | ------------------- | ---------------------------------------------------- |
| `req`   | **Request**         | Contains all the data from the client (user/browser) |
| `res`   | **Response**        | Used to send data back to the client                 |
| `next`  | **Next middleware** | Passes control to the next middleware in the stack   |

---

## 🧱 1. `req` (Request Object)

The `req` object represents the **incoming HTTP request** and contains data like:

### ✅ Common Properties:

| Property      | Description                                                                    |
| ------------- | ------------------------------------------------------------------------------ |
| `req.body`    | Data sent in the body (e.g., form data or JSON — needs body-parser/middleware) |
| `req.params`  | Route parameters (e.g., `/users/:id`)                                          |
| `req.query`   | Query string parameters (e.g., `/search?q=books`)                              |
| `req.headers` | Headers sent by the client                                                     |
| `req.method`  | HTTP method (GET, POST, etc.)                                                  |
| `req.url`     | The requested URL path                                                         |

### 🔸 Example:

```js
app.post('/user/:id', (req, res) => {
  console.log(req.params.id);  // from /user/123
  console.log(req.body.name);  // from form or JSON
});
```

---

## 🧾 2. `res` (Response Object)

The `res` object is used to **send a response** back to the client.

### ✅ Common Methods:

| Method           | Description                                          |
| ---------------- | ---------------------------------------------------- |
| `res.send()`     | Sends plain text, HTML, or JSON                      |
| `res.json()`     | Sends a JSON response                                |
| `res.status()`   | Sets HTTP status code                                |
| `res.redirect()` | Redirects to a different URL                         |
| `res.render()`   | Renders a template (if using a view engine like EJS) |

### 🔸 Example:

```js
app.get('/', (req, res) => {
  res.status(200).json({ message: "Welcome!" });
});
```

---

## 🧩 3. `next` (Next Middleware Function)

* `next()` is a function that, when called, **passes control** to the **next middleware** in the request/response chain.
* It’s useful for building:

  * Authentication checks
  * Validation
  * Logging
  * Error handling

### 🔸 Example Middleware:

```js
const logMiddleware = (req, res, next) => {
  console.log("Request URL:", req.url);
  next(); // Passes to next route or middleware
};

app.use(logMiddleware);
```

If you don’t call `next()`, the request will **hang** and never reach the next function.

---

## 🧪 Real Example Putting All Together

```js
app.get('/product/:id', (req, res, next) => {
  const productId = req.params.id;

  if (!productId) {
    return res.status(400).send("Product ID is required");
  }

  console.log("Fetching product:", productId);
  next(); // passes to next middleware or route
}, (req, res) => {
  res.send("Product loaded successfully");
});
```

---

## 🔥 Custom Error Middleware Example

```js
// Regular route
app.get("/", (req, res) => {
  throw new Error("Something broke!");
});

// Error-handling middleware
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send("Internal Server Error");
});
```

> You MUST use 4 parameters for error middleware: `(err, req, res, next)`

---

## ✅ Summary Table

| Component | What it does       | Example Use                    |
| --------- | ------------------ | ------------------------------ |
| `req`     | Reads request data | `req.body.name`, `req.query.q` |
| `res`     | Sends response     | `res.status(200).json(...)`    |
| `next`    | Passes control     | `next()` in custom middleware  |

---

