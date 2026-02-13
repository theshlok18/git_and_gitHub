

# 🌐 Complete Guide to **Git and GitHub**

---

## 🧠 1. What is Git?.

**Git** is a **distributed version control system** used to track changes in source code during software development. It allows multiple developers to work together on a project without overwriting each other’s work.

### Key Features:
- Tracks every change made to files.
- Enables branching and merging.
- Works offline.
- Lightweight and fast.

---

## 🧑‍💻 2. What is GitHub?

**GitHub** is a **web-based hosting service** for Git repositories. It provides a collaborative environment for developers to share, review, and manage code.

### Key Features:
- Hosting Git repositories online.
- Pull requests and code reviews.
- Issue tracking and project management.
- CI/CD integration (e.g., GitHub Actions).
- Team collaboration tools.

---

## 🛠️ 3. Installing Git

### Windows:
1. Download from [https://git-scm.com](https://git-scm.com)
2. Run the installer.
3. Choose:
   - Use Git from Windows Command Prompt
   - Checkout Windows-style, commit Unix-style line endings
4. Finish installation.

### macOS:
1. Use Homebrew:
   ```bash
   brew install git
   ```

### Linux (Ubuntu):
```bash
sudo apt update
sudo apt install git
```

---

## 🧾 4. Configuring Git

Set your name and email globally:

```bash
git config --global user.name "YourName"
git config --global user.email "you@example.com"
```

To view config:
```bash
git config --list
```

---

## 📁 5. Creating a Local Git Repository

### Initialize a repo:
```bash
git init
```

### Clone an existing repo:
```bash
git clone https://github.com/username/repo-name.git
```

---

## 📝 6. Git Workflow

### 3 Main States:
1. **Working Directory** – Your actual files.
2. **Staging Area (Index)** – Files marked for next commit.
3. **Repository (Git Directory)** – Committed snapshots.

### Basic Commands:
```bash
git add <file>        # Add file to staging area
git add .             # Add all files
git commit -m "Msg"   # Commit changes
git status            # Check repo status
git log               # View commit history
```

---

## 📤 7. Pushing Code to GitHub

### Step-by-step:
1. Create a new repo on GitHub (don’t check “Initialize with README”).
2. Link your local repo:
   ```bash
   git remote add origin https://github.com/username/repo.git
   ```
3. Push code:
   ```bash
   git branch -M main
   git push -u origin main
   ```

---

## 🌐 8. Branching and Merging

### Create a new branch:
```bash
git branch feature-1
```

### Switch to a branch:
```bash
git checkout feature-1
```

Or in one step:
```bash
git checkout -b feature-1
```

### Merge a branch:
```bash
git checkout main
git merge feature-1
```

### Delete a branch:
```bash
git branch -d feature-1
```

---

## 🛡️ 9. Resolving Merge Conflicts

When Git cannot automatically merge changes, it creates a **conflict**.

### Steps to resolve:
1. Open the conflicting file.
2. Look for:
   ```
   <<<<<<< HEAD
   // your changes
   =======
   // incoming changes
   >>>>>>> branch-name
   ```
3. Edit and save the file.
4. Add and commit:
   ```bash
   git add <file>
   git commit -m "Resolved conflict"
   ```

---

## 🔁 10. Syncing with Remote (GitHub)

### Fetch and pull:
```bash
git fetch origin
git pull origin main
```

### Push changes:
```bash
git push origin main
```

---

## 🔐 11. Using SSH with GitHub

### Why SSH?
- No need to enter username/password every time.
- More secure.

### Steps:
1. Generate SSH key:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "you@example.com"
   ```
2. Add to SSH agent:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```
3. Copy the public key:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
4. Add to GitHub: **Settings > SSH and GPG keys > New SSH key**

---

## 🧪 12. Git Tags

Used to mark specific points in history as important (e.g., releases).

### Create a tag:
```bash
git tag v1.0.0
```

### Push tags:
```bash
git push origin v1.0.0
```

---

## 📦 13. Git Stash

Temporarily save changes that aren’t ready to commit.

### Commands:
```bash
git stash
git stash apply
git stash list
```

---

## 📁 14. Ignoring Files with `.gitignore`

Create a `.gitignore` file to tell Git which files **not** to track.

Example `.gitignore`:
```
# Ignore logs
*.log
# Ignore environment files
.env
# Ignore node_modules
node_modules/
```

---

## 🧰 15. Git Tools and GUIs

| Tool | Description |
|------|-------------|
| **VS Code** | Built-in Git support |
| **GitKraken** | Visual Git client |
| **Sourcetree** | Free Git GUI |
| **IDEA / VS** | Integrated Git tools |

---

## 🔄 16. Rewriting Git History

### Amend last commit:
```bash
git commit --amend
```

### Reset to a previous commit:
```bash
git reset --hard <commit-hash>
```

> ⚠️ Use with caution – can delete work.

### Rebase:
```bash
git rebase main
```

---

## 🧑‍🤝‍🧑 17. Collaborating on GitHub

### Fork a repo:
- Click "Fork" on GitHub to create your own copy.

### Clone your fork:
```bash
git clone https://github.com/your-username/repo.git
```

### Create a Pull Request:
- Push changes to your fork.
- Go to GitHub > Compare & pull request.

---

## 🧩 18. Using Pull Requests (PRs)

### Process:
1. Make changes in your branch.
2. Push to GitHub.
3. Go to repo > "Compare & pull request".
4. Add reviewers, write description.
5. Merge after approval.

---

## 🧱 19. Project Management on GitHub

### Features:
- **Issues** – Track bugs, enhancements.
- **Projects** – Kanban-style boards.
- **Milestones** – Group issues by release.
- **Labels** – Categorize issues.
- **Discussions** – Q&A section for community.

---

## 🧪 20. GitHub Actions (CI/CD)

Automate workflows like testing, building, and deploying.

### Example `.github/workflows/ci.yml`:
```yaml
name: CI Pipeline
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: echo "Running tests..."
```

---

## 📦 21. GitHub Packages

Host packages like:
- npm
- Docker
- Maven
- RubyGems

Use in your projects via GitHub’s package registry.

---

## 🧩 22. GitHub Pages

Host static websites directly from a repo.

### Steps:
1. Go to **Settings > Pages**
2. Choose branch and folder
3. Publish

---

## 🧠 23. Git Best Practices

| Practice | Description |
|---------|-------------|
| Small commits | Each commit should do one thing |
| Descriptive messages | e.g., "Fix login bug" |
| Branch per feature | Never work directly on `main` |
| Pull before push | Always sync before pushing |
| Review before merge | Use PRs for collaboration |

---

## 🧪 24. Git Concepts Explained

| Concept | Explanation |
|--------|-------------|
| SHA-1 Hash | Unique identifier for each commit |
| Blob | Git object storing file data |
| Tree | Git object representing a directory |
| Commit | Snapshot of the repo at a point in time |
| Ref | Pointer to a commit (like a branch) |
| Detached HEAD | When you're not on any branch |

---

## 📚 25. Useful Git Commands Reference

| Command | Description |
|--------|-------------|
| `git init` | Initialize new repo |
| `git clone <url>` | Clone repo |
| `git status` | Show current state |
| `git log` | View commit history |
| `git diff` | See changes between commits |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Commit changes |
| `git push` | Upload to remote |
| `git pull` | Fetch and merge |
| `git branch` | List branches |
| `git checkout <branch>` | Switch branch |
| `git merge <branch>` | Merge changes |
| `git stash` | Save changes temporarily |
| `git tag` | Manage tags |

---

## 🎯 26. Git vs GitHub: Summary

| Feature | Git | GitHub |
|--------|-----|--------|
| Type | CLI tool | Web platform |
| Hosting | Local | Cloud |
| Collaboration | No built-in | Yes |
| UI | Terminal | Web UI |
| Access | Offline | Online |
| CI/CD | No | Yes (GitHub Actions) |
| Code Reviews | No | Yes (Pull Requests) |

---

## 📚 27. Learning Resources

- **Official Git Docs**: [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)
- **Pro Git Book** (Free PDF)
- **GitHub Learning Lab**: [https://lab.github.com](https://lab.github.com)
- **Atlassian Git Tutorials**: [https://www.atlassian.com/git/tutorials](https://www.atlassian.com/git/tutorials)
- **Codecademy Git Course**

---

## 🧑‍🏫 28. Git and GitHub for Teams

- Use **Teams** and **Organizations** on GitHub.
- Set **branch protection rules**.
- Use **CODEOWNERS** to assign reviewers.
- Enable **required reviews** and **status checks**.
- Automate with **GitHub Actions** and **Templates**.

---

## 🧩 29. Git Hooks

Custom scripts that run before or after Git events.

### Location:
`.git/hooks/`

Example: `pre-commit`, `post-merge`

---

## 🧵 30. Advanced Git Concepts

| Concept | Description |
|--------|-------------|
| Cherry-pick | Apply a specific commit |
| Rebase vs Merge | Linear history vs merge commit |
| Squash commits | Combine multiple commits |
| Bisect | Find which commit introduced a bug |
| Reflog | Log of all reference changes |
| Submodules | Include external repos |

---

## 🧪 31. Git GUI Clients

| Tool | OS | Features |
|------|----|----------|
| GitKraken | Win/macOS/Linux | Visual graph, easy UI |
| Sourcetree | Win/macOS | Free, Mercurial support |
| VS Code | All | Built-in Git panel |
| IntelliJ IDEA | All | Git integration |
| Tower | macOS/Win | Advanced features |

---

## 🏁 Final Tips

- Always pull before pushing.
- Never commit to `main` directly.
- Use branches for every feature or bug fix.
- Keep `.gitignore` updated.
- Write clear commit messages.
- Use GitHub for collaboration and documentation.
