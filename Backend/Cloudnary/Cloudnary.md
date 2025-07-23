<img width="1425" height="653" alt="Image" src="https://github.com/user-attachments/assets/669c3eea-11a3-4e6e-acc1-6944f46f3e5e" />

## ☁️ What is Cloudinary?

**Cloudinary** is a **cloud-based media management platform** that allows you to:

* **Upload** images, videos, and files
* **Store** them securely
* **Optimize and transform** them on-the-fly (resize, crop, compress, convert formats, etc.)
* **Deliver** them fast via global **CDN**
* **Use APIs and SDKs** for integration with front-end and back-end apps

---

## 🔐 Basic Setup (Web or Node.js)

### 📝 Step 1: Sign Up

* Go to [https://cloudinary.com](https://cloudinary.com)
* Sign up and get your **Cloud name**, **API Key**, and **API Secret**

---

### 📦 Step 2: Install Cloudinary SDK

#### For Node.js:

```bash
npm install cloudinary
```

#### For React/Frontend, use unsigned upload with the Cloudinary Widget (or APIs via backend)

---

### 🔧 Step 3: Configuration

```js
// config/cloudinary.js

import { v2 as cloudinary } from 'cloudinary';

cloudinary.config({
  cloud_name: 'your_cloud_name',
  api_key: 'your_api_key',
  api_secret: 'your_api_secret',
});

export default cloudinary;
```

---

## 📤 Uploading Files (Node.js Backend Example)

```js
import cloudinary from './config/cloudinary.js';
import fs from 'fs';

const uploadToCloudinary = async (localFilePath) => {
  try {
    const result = await cloudinary.uploader.upload(localFilePath, {
      folder: 'your-folder',
    });
    fs.unlinkSync(localFilePath); // Delete local file after upload
    return result;
  } catch (error) {
    fs.unlinkSync(localFilePath); // Delete file on error too
    throw error;
  }
};
```

---

## 🌐 Upload via Frontend (Unsigned Widget or Form Upload)

### With Upload Widget:

```html
<script src="https://upload-widget.cloudinary.com/global/all.js"></script>
<button onclick="openUploadWidget()">Upload Image</button>

<script>
function openUploadWidget() {
  cloudinary.openUploadWidget(
    { cloudName: 'your_cloud_name', uploadPreset: 'your_preset' },
    function (error, result) {
      if (!error && result.event === "success") {
        console.log('Image uploaded:', result.info.secure_url);
      }
    }
  );
}
</script>
```

---

## 🛠️ Transformations (URL-based)

Cloudinary lets you **manipulate images by changing the URL**.

### Example: Resize Image

```js
https://res.cloudinary.com/demo/image/upload/w_300,h_300,c_fill/sample.jpg
```

**Breakdown:**

* `w_300` → width 300px
* `h_300` → height 300px
* `c_fill` → crop to fill
* `sample.jpg` → image name

### Other Transformations:

| Transformation  | Syntax Example          |
| --------------- | ----------------------- |
| Resize          | `w_500,h_500`           |
| Crop            | `c_crop`                |
| Format          | `f_webp`                |
| Quality         | `q_auto`                |
| Blur            | `e_blur:300`            |
| Rounded Corners | `r_20`                  |
| Overlay Text    | `l_text:Arial_30:Hello` |

---

## 📦 Cloudinary Storage Structure

* **Folders** (like Google Drive)
* Every upload has:

  * `public_id`
  * `secure_url`
  * `format`
  * `resource_type` (image, video, raw)

---

## 🔎 Delivery via CDN

All media is delivered from **fast, optimized, cached CDN URLs**, for example:

```js
https://res.cloudinary.com/your_cloud_name/image/upload/v1650000000/sample.jpg
```

---

## 💬 Example Response from Upload

```json
{
  "asset_id": "abc123",
  "public_id": "your-folder/image1",
  "version": 1651234567,
  "url": "http://res.cloudinary.com/.../image1.jpg",
  "secure_url": "https://res.cloudinary.com/.../image1.jpg"
}
```

---

## 📺 Video Uploads

Cloudinary also supports videos:

```js
await cloudinary.uploader.upload("video.mp4", {
  resource_type: "video",
});
```

---

## ✅ Benefits of Cloudinary

* Auto optimization for web (fast loading)
* On-the-fly image and video transformations
* Global CDN delivery
* Secure and scalable
* Easy API & SDK integration

---

## 🔒 Security Tips

* Use **unsigned uploads** for public uploads with **upload presets**
* Use **signed uploads** for private/authenticated uploads

---

## ➕ Bonus: Deleting Media

```js
await cloudinary.uploader.destroy("folder/image1");
```

For video:

```js
await cloudinary.uploader.destroy("folder/video1", { resource_type: "video" });
```

---

