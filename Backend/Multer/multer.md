**Multer** is a **Node.js middleware** for handling `multipart/form-data`, which is **primarily used for uploading files**.

---

### 🔧 What Multer Does:

When users submit forms that include files (like images, videos, or documents), those files are sent to the server in `multipart/form-data` format. Multer helps your Node.js/Express server **parse** this data and **store the files**.

---

### 🔍 Common Use Case:

Uploading profile pictures, documents, product images, etc., through an HTML form.

---

### 🧱 How Multer Works:

* It intercepts the form data before it reaches your route handler.
* Parses out the file data.
* Stores the file either in memory or on disk.
* Passes the remaining data to your request (`req.body`), and the file info to `req.file` (or `req.files` for multiple uploads).

---

### 📦 Install Multer:

```bash
npm install multer
```

---

### 🧪 Example Usage:

```js
import express from 'express';
import multer from 'multer';

const app = express();
const upload = multer({ dest: 'uploads/' }); // Files go to 'uploads' folder

// Single file upload
app.post('/upload', upload.single('profilePic'), (req, res) => {
  console.log(req.file);  // File data
  console.log(req.body);  // Other form fields
  res.send('File uploaded successfully');
});
```

---

### ⚙️ Multer Options:

You can configure:

* `storage` (disk/memory/custom location)
* `fileFilter` (accept or reject files)
* `limits` (max file size, number of files, etc.)

Example with disk storage and file type filtering:

```js
const storage = multer.diskStorage({
  destination: (req, file, cb) => cb(null, 'uploads/'),
  filename: (req, file, cb) => cb(null, Date.now() + '-' + file.originalname)
});

const fileFilter = (req, file, cb) => {
  if (file.mimetype.startsWith('image/')) cb(null, true);
  else cb(new Error('Only images are allowed'), false);
};

const upload = multer({ storage, fileFilter });
```

---

### ✅ Summary:

| Feature      | Description                                  |
| ------------ | -------------------------------------------- |
| Parses       | `multipart/form-data`                        |
| Use case     | File uploads (images, documents, etc.)       |
| Popular with | Express.js                                   |
| Output       | Adds `req.file` / `req.files` to the request |

---

