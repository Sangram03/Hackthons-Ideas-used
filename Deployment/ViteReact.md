## ✅ Vite + React Configuration (GitHub `README.md` Format)

````md
## ⚡ React + Vite Setup

Vite is a modern build tool that provides a faster and leaner development experience for modern web projects. Here’s how you can set up a React project using Vite.

---

### 🛠️ Installation Steps

```bash
# 1. Create a new Vite + React project
npm create vite@latest my-app -- --template react

# 2. Move into the project directory
cd my-app

# 3. Install dependencies
npm install

# 4. Run the development server
npm run dev
````

---

### 📁 Project Structure

```bash
my-app/
├── public/
│   └── vite.svg
├── src/
│   ├── assets/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── .gitignore
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

---

### ⚙️ Vite Config File

```js
// vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000,       // default is 5173
    open: true,       // opens browser automatically
  },
})
```

---

### 🔧 Scripts in `package.json`

```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}
```

---

### 🌍 Deployment (GitHub Pages / Vercel / Netlify)

To deploy:

* **Vercel**: Push repo → Import from Git → Deploy
* **Netlify**:

  * Set build command: `npm run build`
  * Publish directory: `dist`
* **GitHub Pages**:

  * Use [`vite-plugin-gh-pages`](https://www.npmjs.com/package/vite-plugin-gh-pages) or `gh-pages` package
  * Example:

    ```bash
    npm install gh-pages --save-dev
    ```

    ```json
    "scripts": {
      "predeploy": "npm run build",
      "deploy": "gh-pages -d dist"
    }
    ```

---

### 📦 Dependencies

```bash
npm install react react-dom
npm install -D vite @vitejs/plugin-react
```

---

### ✅ Features

* Super fast hot-reloading
* Native ES module support
* Easy configuration
* Optimized production build

---

### 📌 Note

If you're using Tailwind CSS, install it with:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

---

### 📚 Useful Links

* [Vite Docs](https://vitejs.dev/)
* [React Docs](https://react.dev/)
* [Vercel](https://vercel.com/)
* [Netlify](https://netlify.com/)

```

