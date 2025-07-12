## 🚀 Deploying on Netlify

[Netlify](https://www.netlify.com/) is a fast and developer-friendly platform to deploy **static websites**, **React**, **Vite**, and other frontend frameworks — with **free hosting**, custom domains, and CI/CD built-in.

---

## 🛠️ Requirements

* A GitHub/GitLab/Bitbucket account
* Project pushed to GitHub (or ready to drag-and-drop)
* For React/Vite: use `npm run build` to create production files

---

## 🌐 Deployment Methods

### ✅ Method 1: Deploy via Netlify Web UI

1. Go to [https://netlify.com](https://netlify.com)
2. Click **"Log in"** and choose **GitHub**
3. Click **"Add new site" → "Import from Git"**
4. Choose your repo and branch (e.g., `main`)
5. Set **build settings**:

| Setting           | Value                               |
| ----------------- | ----------------------------------- |
| Build command     | `npm run build` (or `vite build`)   |
| Publish directory | `build` (React), `dist` (Vite)      |
| Base directory    | Leave empty (unless using monorepo) |

6. Click **Deploy Site**

🎉 Your app will be live at:

```
https://your-site-name.netlify.app
```

---

### ✅ Method 2: Drag & Drop Deployment

1. Run the build locally:

```bash
npm run build
```

2. Go to [https://app.netlify.com/drop](https://app.netlify.com/drop)
3. Drag and drop the **`build/` or `dist/`** folder into the browser

✔️ Instant hosting, no setup needed.

---

## ⚙️ Example: Deploying a React App

1. Run:

```bash
npm run build
```

2. Folder `build/` is generated
3. Deploy it using the **Netlify UI** or **drag-and-drop**

---

## 📁 Common Publish Directories

| Framework | Build Command   | Publish Directory        |
| --------- | --------------- | ------------------------ |
| React     | `npm run build` | `build/`                 |
| Vite      | `npm run build` | `dist/`                  |
| Angular   | `ng build`      | `dist/project-name/`     |
| HTML/CSS  | *None*          | Root folder or `public/` |

---

## 🔐 Environment Variables

In Netlify dashboard:

1. Go to **Site → Settings → Environment Variables**
2. Add key-value pairs like:

| Key                 | Example Value             |
| ------------------- | ------------------------- |
| `REACT_APP_API_URL` | `https://api.example.com` |

Use them in code like:

```js
const api = process.env.REACT_APP_API_URL;
```

---

## 🧪 Bonus: Redirects for React Router (SPA)

Create a `_redirects` file in your `public/` folder:

```
/*    /index.html   200
```

➡️ This ensures deep links (like `/about`) work correctly with client-side routing.

---

## 🧠 Tips

* Netlify supports HTTPS, custom domains, CI/CD for free!
* Netlify auto-redeploys when you push to GitHub
* Can add Forms, Functions, and Analytics via Netlify dashboard

---

## 📚 Resources

* 🔗 [Netlify Docs](https://docs.netlify.com/)
* 🔗 [Deploy React on Netlify](https://docs.netlify.com/site-deploys/create-deploys/)
* 🔗 [Netlify CLI](https://docs.netlify.com/cli/get-started/)

---

