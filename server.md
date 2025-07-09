`server.js`


**"📄 Server Code"** or similar section for easy understanding:

---

## 📄 Server Code (`server.js`)

```js
import express from 'express'
import cors from 'cors'
import 'dotenv/config'

// App configuration
const app = express()
const port = process.env.PORT || 4000

// Middlewares
app.use(express.json())
app.use(cors())

// API endpoints
app.get('/', (req, res) => {
    res.send("API WORKING");
})

// Start server
app.listen(port, () => console.log("Server Started", port))
```

---

### ✅ Features Used:

| Feature          | Description                                   |
| ---------------- | --------------------------------------------- |
| `express`        | Sets up the backend server and handles routes |
| `cors`           | Enables Cross-Origin Resource Sharing         |
| `dotenv`         | Loads environment variables from `.env` file  |
| `express.json()` | Parses incoming JSON requests                 |

---













Here's how you can write the **README.md** section for setting up and running your Express server project, including the explanation of the code and command:

---

## 📦 Express API Server

A simple Express.js API server with CORS and environment variable support using `dotenv`.

### 🛠️ Tech Stack

* [Express](https://expressjs.com/)
* [CORS](https://www.npmjs.com/package/cors)
* [dotenv](https://www.npmjs.com/package/dotenv)

---

### 📁 Project Structure

```
project-root/
│
├── server.js         # Main Express server file
├── .env              # Environment variables (e.g., PORT)
└── package.json      # NPM project file
```

---

### 📦 Installation

```bash
npm install
```

---

### 📄 .env File

Create a `.env` file in the root folder and add the following:

```env
PORT=4000
```

---

### 🚀 Running the Server

```bash
npm start
```

---

### 🔁 Available Scripts in `package.json`

```json
"scripts": {
  "start": "node server.js",
  "server": "nodemon server.js"
}
```

---

### 🧪 Test the API

After starting the server, open your browser or use Postman to access:

```
GET http://localhost:4000/
```

Response:

```
API WORKING
```

---

Let me know if you want to add **nodemon**, logging, route files, or database connection info!
