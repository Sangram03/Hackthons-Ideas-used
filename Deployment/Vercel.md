## 🚀 Deploying on Vercel

[Vercel](https://vercel.com) is a powerful, fast, and developer-friendly platform to deploy **frontend** (React, Vite, Next.js) and **full-stack apps**.

---

### 🔧 Requirements

* ✅ A GitHub account
* ✅ Project pushed to GitHub
* ✅ Static site (HTML/CSS/JS) or React/Vite/Next.js app

---

### 🌐 Step-by-Step Guide

#### 🔹 1. Push Your Project to GitHub

Make sure your project is pushed to a public or private GitHub repository.

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main
```

---

#### 🔹 2. Go to Vercel

1. Visit: [https://vercel.com](https://vercel.com)
2. Click **"Login"** and choose **GitHub**
3. Authorize Vercel to access your repositories

---

#### 🔹 3. Import Your Project

1. Click **“Add New Project”**
2. Select the GitHub repo you want to deploy
3. Click **“Import”**

---

#### 🔹 4. Configure Build Settings (Optional)

| Framework     | Build Command   | Output Directory  |
| ------------- | --------------- | ----------------- |
| React / Vite  | `npm run build` | `dist` or `build` |
| Next.js       | Auto-detected   | `.next`           |
| Static (HTML) | *None needed*   | Root (`/`)        |

> ⚙️ Vercel auto-detects most frameworks.

---

#### 🔹 5. Deploy! 🚀

* Click **Deploy**
* Wait for the build to finish (\~30 sec)
* Your live site URL will look like:

```
https://your-project-name.vercel.app
```

---

### 💡 Pro Tips

* Update code in GitHub → Vercel auto-redeploys
* Add `vercel.json` for custom configs (routes, env vars)
* Connect a **custom domain** in the Vercel dashboard

---

### 📁 Example: `vercel.json` (Optional)

```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/" }]
}
```

Use this for single-page apps (like React/Vite) with client-side routing.

---

### 📚 Resources

* 🔗 [Vercel Docs](https://vercel.com/docs)
* 🔗 [Vercel GitHub Integration](https://vercel.com/docs/git/vercel-for-github)

---

Let me know if you’d like:

* A deploy badge added (`[![Deploy on Vercel](https://vercel.com/button)]`)
* A React/Vite-specific deployment walkthrough
* A `.md` file version of this for direct upload to your repo
