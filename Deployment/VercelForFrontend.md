To use this in a **Vercel frontend project** (typically a React, Next.js, or other frontend framework), you'll create a `vercel.json` file at the **root of your project**.

### ✅ Here’s the correct `vercel.json` format:

```json
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/"
    }
  ]
}
```

### 🔍 Purpose:

This rewrite rule ensures **all routes fallback to `/index.html`** — useful for **React apps using React Router** or **single-page applications (SPAs)**, allowing client-side routing to handle navigation.

### 📁 File placement:

```
your-project/
├── public/
├── src/
├── vercel.json   ✅ <- place this here
├── package.json
└── ...
```

### ✅ When to use:

* You’re deploying a **React app (Vite, CRA, etc.)**.
* You’re using **React Router** for navigation.
* You want to fix **"404 Not Found"** on refresh for routes like `/about`, `/dashboard`, etc.

<img width="884" height="656" alt="Image" src="https://github.com/user-attachments/assets/21d38a52-c6a9-46a9-b304-4f3da043c91f" />