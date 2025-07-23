```js
const decoded = jwt.verify(token, process.env.JWT_SECRET);
```

This line is part of a Node.js backend (using the `jsonwebtoken` library) to **verify** a JWT (JSON Web Token) and extract the information from it.

---

## 🔍 What This Does

### ✅ `jwt.verify(...)`

This function:

* **Validates** the JWT token using your secret key.
* If valid, it **decodes** the token and returns the **original payload** (e.g. user ID).
* If invalid or expired, it **throws an error**.

---

## 🔄 Full Breakdown of Each Part:

| Part                     | Meaning                                                                                   |
| ------------------------ | ----------------------------------------------------------------------------------------- |
| `token`                  | The JWT string received from the client (usually in the header).                          |
| `process.env.JWT_SECRET` | The **secret key** used to verify the token (should be same one used in `jwt.sign(...)`). |
| `jwt.verify(...)`        | Verifies the signature of the token and checks if it's expired.                           |
| `decoded`                | The **payload** stored in the token, now returned as a JS object.                         |

---

## 🧪 Example Use Case

```js
const jwt = require("jsonwebtoken");

const authMiddleware = (req, res, next) => {
  const authHeader = req.headers.authorization;

  if (!authHeader) {
    return res.status(401).json({ message: "No token provided" });
  }

  const token = authHeader.split(" ")[1]; // Format: "Bearer <token>"

  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = decoded; // attach user info to request
    next();
  } catch (err) {
    return res.status(401).json({ message: "Invalid or expired token" });
  }
};
```

If the token is valid:

```js
console.log(decoded); 
// Output: { id: 'userIdHere', iat: 1723457344, exp: 1723460944 }
```

---

## 📦 What Does `decoded` Contain?

When you create a token like this:

```js
const token = jwt.sign({ id: user._id }, process.env.JWT_SECRET, { expiresIn: "1h" });
```

Then `decoded` will look like this after verification:

```js
{
  id: "123abc456",     // your custom payload
  iat: 1723457344,     // issued at (timestamp)
  exp: 1723460944      // expiration (timestamp)
}
```

---

## 🔐 Secret Key Importance

* `process.env.JWT_SECRET` is the same secret used to **sign** the token.
* If you use a different key during verification, `jwt.verify()` will fail with an error like:

  ```
  JsonWebTokenError: invalid signature
  ```

---

## 🔁 If Token Is Invalid

* Token expired → `TokenExpiredError`
* Signature invalid → `JsonWebTokenError`
* Token malformed → `SyntaxError`

Always use try-catch:

```js
try {
  const decoded = jwt.verify(token, secret);
} catch (err) {
  return res.status(401).json({ message: "Unauthorized" });
}
```

---

## ✅ Summary

| Part                        | Description                                              |
| --------------------------- | -------------------------------------------------------- |
| `jwt.verify(token, secret)` | Validates and decodes the JWT                            |
| `token`                     | JWT string from client                                   |
| `process.env.JWT_SECRET`    | Secret used to verify the signature                      |
| `decoded`                   | Original payload (e.g. user ID) extracted from the token |
| Use Case                    | Authentication, identifying the user making the request  |

---

