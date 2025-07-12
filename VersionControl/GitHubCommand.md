## 🐙 GitHub Command Reference & Workflow Guide

### 📦 1. Setup & Configuration

| Command                                            | Description                           |
| -------------------------------------------------- | ------------------------------------- |
| `git config --global user.name "Your Name"`        | Set your Git username globally        |
| `git config --global user.email "you@example.com"` | Set your Git email globally           |
| `ssh-keygen -t ed25519 -C "you@example.com"`       | Generate SSH key to link with GitHub  |
| `gh auth login`                                    | Login to GitHub via CLI (interactive) |

---

### 📁 2. Create a Local Repo & Link to GitHub

| Command                            | Description                              |
| ---------------------------------- | ---------------------------------------- |
| `git init`                         | Initialize a new local Git repo          |
| `gh repo create`                   | Create a new GitHub repo (from CLI)      |
| `git remote add origin <repo-url>` | Link local repo to GitHub                |
| `git branch -M main`               | Rename branch to `main` (GitHub default) |
| `git push -u origin main`          | Push first commit and set upstream       |

---

### 🚀 3. Clone from GitHub

```bash
git clone https://github.com/username/repo-name.git
```

> 📁 Downloads the entire repository locally.

---

### 📝 4. Staging & Committing

| Command                        | Description                     |
| ------------------------------ | ------------------------------- |
| `git status`                   | Check what’s modified or staged |
| `git add <filename>`           | Stage one file                  |
| `git add .`                    | Stage all changes               |
| `git commit -m "your message"` | Save changes with a message     |

---

### 🔄 5. Push & Pull

| Command                | Description             |
| ---------------------- | ----------------------- |
| `git push origin main` | Push changes to GitHub  |
| `git pull origin main` | Pull latest from GitHub |

---

### 🌿 6. Branching & Collaboration

| Command                    | Description                         |
| -------------------------- | ----------------------------------- |
| `git branch`               | Show all branches                   |
| `git branch <name>`        | Create a new branch                 |
| `git checkout <name>`      | Switch to another branch            |
| `git checkout -b <name>`   | Create and switch to a branch       |
| `git merge <branch>`       | Merge a branch into the current one |
| `git push origin <branch>` | Push a branch to GitHub             |
| `gh pr create`             | Create a pull request (GitHub CLI)  |
| `gh pr view`               | View pull request details           |
| `gh pr checkout <number>`  | Checkout a PR branch from GitHub    |

---

### 🔧 7. GitHub-Specific Features

| Feature                 | Command                 |
| ----------------------- | ----------------------- |
| 🔐 Create Repo from CLI | `gh repo create <name>` |
| 🚀 Open Repo in Browser | `gh repo view --web`    |
| 👀 View Issues          | `gh issue list`         |
| 🛠 Create Issue         | `gh issue create`       |
| 🔃 Fork a Repo          | `gh repo fork`          |
| ⭐ Star a Repo           | `gh repo star <repo>`   |
| ❌ Delete a Repo         | `gh repo delete`        |

---

### 🗂 8. .gitignore and Best Practices

* Use `.gitignore` to prevent tracking:

```bash
node_modules/
.env
dist/
.DS_Store
```

---

## ✅ Example Workflow

```bash
git init
gh repo create
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/user/repo.git
git push -u origin main
```

---

### 📚 Resources

* 🔗 [GitHub Docs](https://docs.github.com/)
* 🔗 [Git CLI Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
* 🔗 [GitHub CLI Guide](https://cli.github.com/manual/)

---

