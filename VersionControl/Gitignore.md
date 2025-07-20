Here's a **complete `.gitignore`** template that covers a **full-stack JavaScript/TypeScript project**, including:

* Node.js (Express/MongoDB)
* React or Vite (Frontend)
* Environment files
* OS/editor-specific junk
* Build, logs, coverage, database dumps

This is ideal for most full-stack apps, and you can copy-paste directly into your `.gitignore` file.

---

## 📁 `.gitignore` (Full-Stack JavaScript Project)

```gitignore
####################################
# 📦 Node.js / Express / Backend
####################################
node_modules/
.env
.env.*.local
.env.local
.env.production
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pids/
*.pid
*.seed
*.pid.lock

# Optional MongoDB dump dir
dump/

# Process manager logs
*.log
logs/
pm2.log

# Cache
.cache/
.tmp/
temp/

####################################
# 💻 React / Vite / Frontend
####################################
# React
build/

# Vite
dist/

# Frontend node_modules (if separated)
frontend/node_modules/
frontend/build/
frontend/dist/

# Vite cache
.vite/

####################################
# ⚙️ TypeScript
####################################
*.tsbuildinfo

####################################
# 📋 Test coverage
####################################
coverage/
*.lcov

####################################
# 🧪 Jest
####################################
jest-test-results.json

####################################
# 🧠 ESLint / Prettier
####################################
.eslintcache

####################################
# 🧰 OS/IDE/editor files
####################################
.DS_Store
Thumbs.db
*.swp

# VSCode
.vscode/

# JetBrains
.idea/
*.iml

# Windows
ehthumbs.db
Icon?
Desktop.ini

# Mac system files
.Spotlight-V100
.Trashes

# Linux
*~
```

---

### ✅ Bonus Tips:

* Add a `README.md`, `.env.example`, and `LICENSE` — but **do not** add `.env` or `node_modules/`.
* You can customize this if you're using **Next.js**, **Nuxt**, **NestJS**, etc.
