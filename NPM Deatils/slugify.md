### ✅ Step 1: Install `slugify`

Run this in your terminal:

```bash
npm install slugify
```

---

### ✅ Step 2: Use `slugify` in Your Code

#### 📦 Basic Example

```js
const slugify = require('slugify');

const title = "React Toastify Notification App";
const slug = slugify(title);

console.log(slug); // Output: react-toastify-notification-app
```

---

### ✅ Advanced Usage (with options)

You can pass an **options object** to customize the output:

```js
const slugify = require('slugify');

const slug = slugify("Hello World!", {
  lower: true,         // convert to lowercase
  strict: true,        // remove special characters
  trim: true,          // remove leading/trailing spaces
  remove: /[*+~.()'"!:@]/g // remove specific characters using regex
});

console.log(slug); // Output: hello-world
```

---

### ✅ In ES Modules (ESM)

If you're using `type: "module"` in `package.json`, import it like this:

```js
import slugify from 'slugify';

console.log(slugify('My New Blog Post')); // my-new-blog-post
```

---

### 🔧 Real-world Use Case

You might use it for creating blog post URLs like:

```js
const postTitle = "10 Tips for Learning React!";
const postSlug = slugify(postTitle, { lower: true });

console.log(`https://myblog.com/posts/${postSlug}`);
// Output: https://myblog.com/posts/10-tips-for-learning-react
```