## 🚀 Git Command Cheat Sheet

| 🔢 No. | 🛠️ Command                                        | 💬 Description                                            |
| ------ | -------------------------------------------------- | --------------------------------------------------------- |
| 01     | `git init`                                         | Initialize a new Git repository in the current directory  |
| 02     | `git clone <repo-url>`                             | Clone a remote repo to your local system                  |
| 03     | `git status`                                       | Show the current status of files (staged, modified, etc.) |
| 04     | `git add <file>`                                   | Stage a specific file for commit                          |
| 05     | `git add .`                                        | Stage **all** changes in the current directory            |
| 06     | `git commit -m "message"`                          | Commit staged changes with a message                      |
| 07     | `git log`                                          | View commit history                                       |
| 08     | `git branch`                                       | List all branches                                         |
| 09     | `git branch <name>`                                | Create a new branch                                       |
| 10     | `git checkout <branch>`                            | Switch to a different branch                              |
| 11     | `git checkout -b <name>`                           | Create and switch to a new branch                         |
| 12     | `git merge <branch>`                               | Merge another branch into the current one                 |
| 13     | `git pull`                                         | Pull latest changes from remote repository                |
| 14     | `git push`                                         | Push local commits to remote repository                   |
| 15     | `git remote -v`                                    | Show remote repository URLs                               |
| 16     | `git remote add origin <url>`                      | Link local repo to a remote GitHub repo                   |
| 17     | `git push -u origin main`                          | Push and set the upstream (first time)                    |
| 18     | `git diff`                                         | Show differences between working directory and index      |
| 19     | `git rm <file>`                                    | Remove a file and stage the deletion                      |
| 20     | `git stash`                                        | Temporarily save changes without committing               |
| 21     | `git stash pop`                                    | Reapply stashed changes                                   |
| 22     | `git reset --hard`                                 | Reset all changes to last commit (⚠️ careful)             |
| 23     | `git clean -fd`                                    | Remove all untracked files and folders (⚠️ careful)       |
| 24     | `git config --global user.name "Your Name"`        | Set your Git username                                     |
| 25     | `git config --global user.email "you@example.com"` | Set your Git email                                        |
| 26     | `git config --list`                                | Show all current Git configurations                       |

---

## 📦 GitHub-Specific Commands

| Command                                      | Description                                             |
| -------------------------------------------- | ------------------------------------------------------- |
| `gh repo create`                             | Create a GitHub repo from the command line (GitHub CLI) |
| `gh auth login`                              | Authenticate GitHub CLI                                 |
| `git push origin <branch>`                   | Push branch to remote                                   |
| `git clone https://github.com/user/repo.git` | Clone a GitHub repo                                     |

---

## 🧠 Pro Tips

* ✅ Always run `git status` before committing
* 💬 Write clear and meaningful commit messages
* 🔁 Use branches for new features or bug fixes
* 📦 `.gitignore` is used to ignore files/folders from tracking

---
