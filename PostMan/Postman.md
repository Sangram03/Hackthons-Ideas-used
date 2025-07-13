## 🔶 What is Postman?

**Postman** is a popular API client that allows developers to:

* Send HTTP requests (GET, POST, PUT, DELETE, etc.)
* Test and debug REST APIs
* Organize requests into collections
* Automate testing
* View responses clearly

---

## ✅ How to Install Postman

1. Visit: [https://www.postman.com/downloads/](https://www.postman.com/downloads/)
2. Download and install for your OS (Windows/macOS/Linux)
3. Open and sign in (or use as a guest)

---

## ✅ Basic Features & Use Cases

| Feature                 | Description                                  |
| ----------------------- | -------------------------------------------- |
| **Collections**         | Save and organize API requests               |
| **Environments**        | Use environment variables like `{{baseUrl}}` |
| **History**             | Keeps track of previously sent requests      |
| **Tests**               | Write tests to validate response data        |
| **Pre-request Scripts** | Write JS to run before requests              |

---

## ✅ Sending a Basic Request

### 🔹 Example: Sending a POST request

Assume you have a route in Express:

```js
app.post('/api/login', (req, res) => {
  const { email, password } = req.body;
  res.json({ message: "Login successful" });
});
```

### 🔹 Steps in Postman:

1. **Open Postman**
2. **Set Method** to `POST`
3. **Enter URL**: `http://localhost:5000/api/login`
4. Go to the **Body** tab → Select **raw** → Choose `JSON`
5. Enter JSON data:

   ```json
   {
     "email": "test@example.com",
     "password": "123456"
   }
   ```
6. Click **Send**
7. ✅ You'll see the response like:

   ```json
   {
     "message": "Login successful"
   }
   ```

---

## ✅ Types of Requests You Can Send

| Method     | Purpose                    |
| ---------- | -------------------------- |
| **GET**    | Fetch data from the server |
| **POST**   | Send data to the server    |
| **PUT**    | Update data                |
| **DELETE** | Delete data                |
| **PATCH**  | Partial update             |

---

## ✅ Headers Tab (Common Use)

* Set `Content-Type: application/json`
* Add `Authorization: Bearer <token>` if using JWT

---

## ✅ Tests in Postman

You can write JavaScript-based tests in the **Tests** tab. Example:

```js
pm.test("Status code is 200", function () {
  pm.response.to.have.status(200);
});
```

---

## ✅ Saving & Organizing Requests

* Click **Save** after making a request
* Create **Collections** to group related API calls
* Add **folders** inside collections for each module (e.g. Auth, Users, Products)

---

## ✅ Environment Variables (Optional)

Create variables like:

| Variable Name | Initial Value           |
| ------------- | ----------------------- |
| `baseUrl`     | `http://localhost:5000` |
| `authToken`   | `eyJhbGciOiJIUzI1...`   |

Then in requests:

* URL: `{{baseUrl}}/api/user`
* Header: `Authorization: Bearer {{authToken}}`

---

## ✅ Automation & Testing Collections

Use **Collection Runner** to:

* Run all requests in a collection
* Add test scripts to verify outputs
* Generate test reports

---

## ✅ Example Use Case: Full Flow

1. **POST /api/register** → register new user
2. **POST /api/login** → get JWT token
3. **GET /api/user** → fetch data with token

   * Add `Authorization: Bearer <token>` in Headers

---

## 🧪 Summary

| Task                     | Postman Feature |
| ------------------------ | --------------- |
| Test your API endpoints  | Requests        |
| Automate login workflows | Collections     |
| Reuse base URLs          | Environments    |
| Simulate frontend calls  | Headers + Body  |
| Run automated tests      | Tests tab       |

---

Let me know if you want:

* Example test collection (JSON export)
* How to test file upload (with `form-data`)
* How to test protected routes with JWT

I'll guide you with code and setup too.
