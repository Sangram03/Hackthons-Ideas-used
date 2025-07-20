`cookie-parser` is a **middleware** for Express.js used to **parse cookies** attached to the client request object.

---

### 🔍 What are Cookies?

Cookies are small pieces of data sent by the server and stored in the client’s browser. They are sent back to the server with every request and often used for:

* Authentication sessions
* Tracking user activity
* Storing preferences

---

### 🍪 What Does `cookie-parser` Do?

When a browser sends a request to your Express server, any cookies are included in the request header. The `cookie-parser` middleware reads these cookies and makes them available on `req.cookies` (and `req.signedCookies` for signed cookies).

---

### ✅ Basic Usage:

**Installation:**

```bash
npm install cookie-parser
```

**In your Express app:**

```js
import express from 'express';
import cookieParser from 'cookie-parser';

const app = express();

// Use cookie-parser middleware
app.use(cookieParser()); // You can also pass a secret string for signed cookies

app.get('/', (req, res) => {
  console.log(req.cookies); // Logs any cookies sent by the client
  res.send('Cookies parsed!');
});
```

---

### 🔐 Signed Cookies:

If you want to ensure that a cookie wasn’t tampered with, use a **secret**:

```js
app.use(cookieParser('your_secret_key'));

app.get('/set-cookie', (req, res) => {
  res.cookie('token', '123abc', { signed: true });
  res.send('Signed cookie set');
});

app.get('/read-cookie', (req, res) => {
  console.log(req.signedCookies); // Access signed cookies
  res.send('Reading signed cookies');
});
```

---

### 🧠 Summary:

| Feature          | Description                                            |
| ---------------- | ------------------------------------------------------ |
| Parses cookies   | Parses `Cookie` header into `req.cookies` object       |
| Supports signing | Allows verification of cookie integrity using a secret |
| Easy to use      | One line middleware integration in Express             |

