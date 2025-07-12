## 🌐 Deploying on Render

[**Render**](https://render.com) is a cloud platform where you can deploy **full-stack apps**, including **Node.js**, **Express**, **MongoDB**, and static websites — with free plans for hobby use.

---

### ✅ What You Can Deploy

| Type                         | Supported |
| ---------------------------- | --------- |
| Static Sites (HTML/CSS/JS)   | ✅ Yes     |
| Node.js / Express Backend    | ✅ Yes     |
| Full Stack (with MongoDB)    | ✅ Yes     |
| React / Vite Frontend        | ✅ Yes     |
| PostgreSQL / Redis Databases | ✅ Yes     |

---

## 🚀 Render Deployment: Step-by-Step

### 🔹 1. Push Your Project to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main
```

---

### 🔹 2. Create a Render Account

* Go to [https://render.com](https://render.com)
* Sign up with GitHub
* Authorize access to your repos

---

### 🔹 3. Choose a Service Type

Render offers multiple types of deployments:

| Option                | Use Case              |
| --------------------- | --------------------- |
| **Static Site**       | React, HTML, Vite     |
| **Web Service**       | Node.js, Express apps |
| **Background Worker** | Cron jobs, queues     |
| **Database**          | PostgreSQL, Redis     |

---

### 📁 Example 1: Deploy a Static React/Vite App

1. Select **"Static Site"**
2. Connect your GitHub repo
3. Fill in the details:

| Setting           | Value                            |
| ----------------- | -------------------------------- |
| Build Command     | `npm run build`                  |
| Publish Directory | `build` (React) or `dist` (Vite) |

4. Click **"Create Static Site"**

> ⚠️ For React Router apps, use a `_redirects` file to support routing:

```
/*  /index.html  200
```

---

### ⚙️ Example 2: Deploy a Node.js App

1. Select **“Web Service”**
2. Connect your backend repo
3. Fill in the settings:

| Setting       | Value                                     |
| ------------- | ----------------------------------------- |
| Start Command | `node index.js` or `npm start`            |
| Build Command | `npm install`                             |
| Environment   | Node                                      |
| Branch        | `main` or `master`                        |
| Port          | `4000`, `5000`, or use `process.env.PORT` |

> ✅ Make sure your app uses a dynamic port like this:

```js
const port = process.env.PORT || 4000;
app.listen(port, () => console.log(`Server on ${port}`));
```

---

### 🔐 4. Add Environment Variables (if needed)

For example:

| Key          | Value                        |
| ------------ | ---------------------------- |
| `MONGO_URI`  | your MongoDB Atlas URI       |
| `JWT_SECRET` | your app's secret key        |
| `PORT`       | leave empty (Render sets it) |

---

### 🌐 5. Done! Your site will be live at:

```
https://your-app-name.onrender.com
```

Render will auto-redeploy every time you push to GitHub.

---

### 📚 Resources

* 🔗 [Render Docs](https://render.com/docs)
* 🔗 [Deploy Express App](https://render.com/docs/deploy-node-express-app)
* 🔗 [Static Site Guide](https://render.com/docs/deploy-create-react-app)

---

### 💡 Pro Tips

* Use `.env` files locally, then manually set env vars in Render
* Add a `build` or `start` script in `package.json`
* Monitor logs in the Render dashboard

---

