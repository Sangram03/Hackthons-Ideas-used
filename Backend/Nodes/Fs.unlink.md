## 🧠 What is `fs.unlink`?

`fs.unlink()` is a built-in Node.js method used to **delete a file** from the file system **asynchronously**.

There’s also a synchronous version called `fs.unlinkSync()`.

---

## ✅ Syntax

### 1. Asynchronous (Recommended)

```js
const fs = require("fs");

fs.unlink(path, callback);
```

* **`path`** → String: path to the file you want to delete
* **`callback`** → Function: called when the deletion is complete (or if an error occurs)

### 2. Synchronous

```js
fs.unlinkSync(path);
```

* Same as above, but blocks the event loop until the operation finishes

---

## 📦 Example: Asynchronous Deletion

```js
const fs = require("fs");

fs.unlink("uploads/image.jpg", (err) => {
  if (err) {
    return console.error("Error deleting file:", err.message);
  }
  console.log("File deleted successfully");
});
```

---

## 🧪 Example: Inside an Express Route

```js
const fs = require("fs");
const express = require("express");
const app = express();

app.delete("/delete-image", (req, res) => {
  const filePath = "./uploads/" + req.query.name;

  fs.unlink(filePath, (err) => {
    if (err) {
      return res.status(500).json({ success: false, message: "Delete failed", error: err.message });
    }
    res.json({ success: true, message: "File deleted successfully" });
  });
});
```

---

## 🔄 Synchronous Version

⚠️ Use with caution — blocks the event loop (can affect performance):

```js
try {
  fs.unlinkSync("uploads/image.jpg");
  console.log("File deleted");
} catch (err) {
  console.error("Delete failed:", err.message);
}
```

---

## ⚠️ Error Handling

If the file doesn't exist or there's a permission issue, you'll get an error like:

```bash
ENOENT: no such file or directory, unlink 'uploads/image.jpg'
```

Always check `err.code` to handle specific cases.

---

## ✅ Common Use Cases

* Deleting uploaded images (e.g. profile pictures)
* Cleaning temporary files
* Removing logs or backups on server shutdown
* File versioning (delete old before save new)

---

## 🔐 Pro Tips

* Ensure file paths are **validated** and **safe** (to prevent deleting sensitive files).
* Use `fs.existsSync(path)` or `fs.stat()` to check if a file exists **before deleting**.
* Consider using `path.join()` to avoid OS path issues.

---

## 📌 Summary

| Function          | Description                                                      |
| ----------------- | ---------------------------------------------------------------- |
| `fs.unlink()`     | Deletes a file asynchronously                                    |
| `fs.unlinkSync()` | Deletes a file synchronously                                     |
| Returns           | `undefined` (but you use the callback to handle success/failure) |

---

