### 📦 `req.headers` in Node.js / Express

`req.headers` refers to the **HTTP request headers** sent by the client (like a browser, app, or third-party service) to your server.

---

### 🧠 What are HTTP headers?

HTTP headers are key-value pairs sent in HTTP requests and responses to pass **metadata** (information **about** the data).

For example:

* What kind of data is being sent (`Content-Type`)
* Who is sending it (`User-Agent`)
* Authentication details (`Authorization`)
* Security info (`Signature`, `X-Webhook-Signature`)

---

### 🔹 Syntax in Express.js

```js
app.post('/webhook', (req, res) => {
  console.log(req.headers);
});
```

This logs all the headers the client sent with the request.

---

### ✅ Example Output of `req.headers`

```js
{
  host: 'localhost:3000',
  connection: 'keep-alive',
  'content-length': '123',
  'content-type': 'application/json',
  'user-agent': 'PostmanRuntime/7.28.4',
  'x-webhook-signature': 'abcd1234xyz'
}
```

---

### 🔐 Common Use Cases

| Header                                | Purpose                                        |
| ------------------------------------- | ---------------------------------------------- |
| `Content-Type`                        | Type of data (`application/json`, `text/html`) |
| `Authorization`                       | API keys, JWT tokens, etc.                     |
| `User-Agent`                          | Info about client software                     |
| `X-Signature` / `X-Webhook-Signature` | For verifying webhooks                         |
| `Accept`                              | What response types the client accepts         |

---

### ✅ Real-life Use: Razorpay or Stripe Webhook Verification

```js
const signature = req.headers['x-razorpay-signature'];

const body = JSON.stringify(req.body);

const isValid = verifySignature(signature, body);
```

Here:

* `req.headers['x-razorpay-signature']` = Razorpay’s signature
* `req.body` = webhook payload
* You verify the signature using both

---

### 🧪 Tip: Header names are lowercase

In Express/Node.js, all header names are automatically lowercased.
So:

```js
req.headers['Content-Type']  // ❌ undefined
req.headers['content-type']  // ✅ correct
```

---

