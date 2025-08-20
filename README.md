# 🚀 Git & GitHub Guide: Master Commands and Workflows

📚 **The ultimate guide to Git and GitHub for all developers**  
Learn Git commands, GitHub workflows, and best practices. From beginner basics to advanced operations, this guide is your go-to resource for mastering version control. Perfect for young developers, experienced coders, and veterans.

🔍 **Search Keywords**: Git commands, GitHub tutorial, learn Git, GitHub guide, version control, Git cheatsheet, Git workflows, Git for beginners, advanced Git, GitHub collaboration.

---

## 🎯 Why This Guide?

This guide is designed to help you:
- 🏗️ Set up repositories quickly.
- ⚡ Master daily Git commands.
- 🌿 Manage branches and resolve conflicts.
- 🚀 Collaborate on GitHub with pull requests and forks.
- 🛠️ Use advanced Git features like hooks and rebasing.
- 🆘 Recover from mistakes with emergency commands.

**For All Levels**:
- **Beginners**: Step-by-step instructions with clear examples.
- **Intermediate**: Practical workflows for team projects.
- **Advanced**: Power commands and automation tips.

---

## 📋 Table of Contents

🔍 Click to jump to sections:

### 📖 Core Git Operations
- [🏗️ Repository Setup](#🏗️-repository-setup)
- [📥 Cloning Repositories](#📥-cloning-repositories)
- [⚡ Basic Commands](#⚡-basic-commands)
- [🌿 Branch Management](#🌿-branch-management)
- [⚔️ Handling Conflicts](#⚔️-handling-conflicts)

### 🛠️ Advanced Git Features
- [📦 Stashing Changes](#📦-stashing-changes)
- [📖 Viewing History & Changes](#📖-viewing-history--changes)
- [↩️ Undoing Changes](#↩️-undoing-changes)
- [🌐 Remote Management](#🌐-remote-management)
- [🏷️ Tags & Releases](#🏷️-tags--releases)

### 🚀 GitHub Workflows
- [🔄 Pull Requests & Collaboration](#🔄-pull-requests--collaboration)
- [⚙️ Git Configuration](#⚙️-git-configuration)
- [🛠️ Git Hooks](#🛠️-git-hooks)

### 🔧 Analysis & Troubleshooting
- [📊 Repository Statistics](#📊-repository-statistics)
- [🔒 Security & Credentials](#🔒-security--credentials)
- [🐛 Debugging Git Issues](#🐛-debugging-git-issues)
- [💡 Pro Tips & Best Practices](#💡-pro-tips--best-practices)
- [🆘 Emergency Commands](#🆘-emergency-commands)

### 🤝 Contributing
- [📝 How to Contribute](#📝-how-to-contribute)

---

## 🏗️ Repository Setup

📂 Initialize and configure Git repositories.

### ✨ **Create a New Repository** (Beginner)

```bash
# Create README
echo "# My Project" >> README.md

# Initialize Git
git init -b main

# Stage files
git add README.md

# Commit
git commit -m "Initial commit"

# Add remote (HTTPS for beginners, SSH for secure access)
git remote add origin https://github.com/username/repository.git
# OR git remote add origin git@github.com:username/repository.git

# Push
git push -u origin main
```

> 💡 **Tip**: Use HTTPS for public repos; SSH for private ones.

### 🔗 **Existing Project** (Intermediate)

```bash
# Initialize if needed
git init -b main

# Add files
git add .

# Commit
git commit -m "Add existing project"

# Add remote
git remote add origin https://github.com/username/repository.git

# Push
git push -u origin main
```

### 📁 **Bare Repository** (Advanced)

```bash
git init --bare repo.git
```

> 📚 **Use Case**: Bare repos are for servers without working directories.

---

## 📥 Cloning Repositories

📋 Download repositories from GitHub.

| Method | Command | Best For |
|--------|---------|----------|
| HTTPS | `git clone https://github.com/username/repo.git` | Public repos |
| SSH | `git clone git@github.com:username/repo.git` | Private repos with SSH |
| GitHub CLI | `gh repo clone username/repo` | CLI users |

### 🌿 **Clone Specific Branch** (Intermediate)

```bash
git clone -b feature-branch --single-branch https://github.com/username/repo.git
```

### 🎯 **Sparse Checkout** (Advanced)

```bash
git clone --sparse https://github.com/username/repo.git
cd repo
git sparse-checkout init --cone
git sparse-checkout set src docs
```

> 💡 **SEO Tip**: Search for "Git clone specific folder" to find this section!

---

## ⚡ Basic Commands

🔄 Everyday Git operations.

### 🔍 **Check Status**

```bash
git status  # Full status
git status -s  # Short status
```

| Symbol | Meaning |
|--------|---------|
| ?? | Untracked file |
| A | Staged for commit |
| M | Modified |

### ➕ **Stage Files**

```bash
git add file.txt  # Specific file
git add .  # All files
git add -p  # Interactive staging
```

### 💾 **Commit Changes**

```bash
git commit -m "Add feature X"  # Standard
git commit -am "Update docs"  # Stage and commit
git commit --amend  # Edit last commit
```

> 💡 **Commit Tip**: Use `feat:`, `fix:`, `docs:` prefixes for clarity.

### 🚀 **Push & Pull**

```bash
git push  # Push to remote
git pull  # Fetch and merge
git fetch  # Fetch without merging
git pull --rebase  # Linear history
```

> 📚 **Beginner Workflow**: `git status` → `git add .` → `git commit -m "msg"` → `git push`

---

## 🌿 Branch Management

🌳 Organize work with branches.

### 🆕 **Create & Switch**

```bash
git switch -c feature/new  # Create and switch (Git 2.23+)
git checkout -b feature/new  # Traditional
git switch main  # Switch back
```

### 📋 **List & Delete**

```bash
git branch -a  # List all
git branch -d old-branch  # Delete merged
git push origin --delete old-branch  # Delete remote
```

### 🔄 **Merge & Rebase**

```bash
git checkout main
git merge feature/new  # Merge
git rebase main  # Rebase for clean history
```

> ⚠️ **Beginner Note**: Use merge for simplicity; rebase for linear history (advanced).

---

## ⚔️ Handling Conflicts

🛠️ Resolve merge conflicts step-by-step.

1. **Identify**: `git status`
2. **Edit**: Fix files with conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
3. **Stage**: `git add file`
4. **Commit**: `git commit`

### 🛠️ **Merge Tool** (Advanced)

```bash
git config --global merge.tool vscode
git mergetool
```

> 💡 **Prevent Conflicts**: Regularly `git pull --rebase`.

---

## 📦 Stashing Changes

📦 Save work temporarily.

```bash
git stash  # Save changes
git stash list  # View stashes
git stash apply  # Restore latest
git stash pop  # Restore and remove
git stash -m "WIP on feature"  # Named stash
```

> 📚 **Use Case**: Switch branches without committing.

---

## 📖 Viewing History & Changes

🔍 Explore repository history.

```bash
git log --oneline --graph  # Visual history
git diff  # Unstaged changes
git show commit-id  # Specific commit
```

> 💡 **Advanced**: `git log -p` for detailed diffs.

---

## ↩️ Undoing Changes

↩️ Fix mistakes safely.

| Command | Use Case |
|---------|----------|
| `git restore file` | Discard changes |
| `git reset --soft HEAD~1` | Undo commit, keep changes |
| `git revert commit-id` | Create undo commit |
| `git reset --hard` | Reset everything (caution!) |

> 📚 **Recovery**: Use `git reflog` to find lost commits.

---

## 🌐 Remote Management

🌐 Work with GitHub remotes.

```bash
git remote -v  # List remotes
git remote add upstream url  # Add remote
git fetch upstream  # Sync
```

> 💡 **Team Tip**: Use multiple remotes for collaboration.

---

## 🏷️ Tags & Releases

🏷️ Mark versions for releases.

```bash
git tag v1.0  # Create
git tag -a v1.0 -m "Release v1.0"  # Annotated
git push --tags  # Push to GitHub
```

> 📚 **GitHub Tip**: Tags create releases automatically.

---

## 🔄 Pull Requests & Collaboration

🔄 Work with GitHub features.

- **Create PR**: `gh pr create` or use GitHub UI.
- **Fork Workflow**:
  ```bash
  git clone your-fork
  git switch -c feature/x
  git push origin feature/x
  # Create PR on GitHub
  ```

> 💡 **Beginner**: Fork repos to contribute safely.

---

## ⚙️ Git Configuration

⚙️ Personalize Git.

```bash
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
git config --global core.editor vscode
git config --global alias.st status  # Shortcut
```

> 📚 **Pro Tip**: Add aliases like `alias.co = checkout`.

---

## 🛠️ Git Hooks

🛠️ Automate tasks.

**Example Pre-Commit Hook**:
```bash
#!/bin/sh
npm run lint
```
Save as `.git/hooks/pre-commit` (make executable).

> 💡 **Advanced**: Use Husky for modern hooks.

---

## 📊 Repository Statistics

📊 Analyze contributions.

```bash
git shortlog -sn  # Commits by author
git blame file  # Line-by-line authorship
git log --stat  # File changes
```

> 📚 **Tool**: Install `git-extras` for more stats.

---

## 🔒 Security & Credentials

🔒 Secure your Git setup.

```bash
git config --global credential.helper cache  # Cache credentials
ssh-keygen -t ed25519  # Generate SSH key
git commit -S -m "Signed commit"  # GPG signing
```

> ⚠️ **Tip**: Use GitHub Personal Access Tokens for HTTPS.

---

## 🐛 Debugging Git Issues

🐛 Fix common problems.

| Issue | Solution |
|-------|----------|
| Detached HEAD | `git checkout main` |
| Push rejected | `git pull --rebase` |
| LFS errors | `git lfs install` |

> 📚 **Debug**: Check `git --version`.

---

## 💡 Pro Tips & Best Practices

💡 Level up your Git game.

- Commit small, focused changes.
- Use `.gitignore` for unnecessary files.
- Review PRs carefully.
- **Advanced**: Try `git worktree` for parallel branches.

---

## 🆘 Emergency Commands

🆘 Recover from disasters.

```bash
git reflog  # View history
git reset --hard HEAD@{1}  # Recover state
git fsck --lost-found  # Find lost commits
```

> ⚠️ **Caution**: Backup before drastic resets.

---

## 📝 How to Contribute

🤝 Help improve this guide!

1. **Fork**: Click "Fork" on GitHub.
2. **Clone**: `git clone your-fork`.
3. **Branch**: `git switch -c fix/typo`.
4. **Edit & Commit**: Use `feat:`, `fix:`, `docs:` prefixes.
5. **Push**: `git push origin fix/typo`.
6. **PR**: Create via GitHub UI.

**Guidelines**:
- Test commands.
- Follow existing style.
- Add examples.

> 💡 **SEO Tip**: Search "contribute to GitHub guide" to find this section.

---

## 🏆 Why Contribute?

- ✨ Get listed in contributors.
- 🌟 Gain visibility in the community.
- 💪 Learn Git hands-on.

**Communication**:
- Issues: Report bugs/features.
- PR Comments: Discuss changes.
- Discussions: Share ideas.

---

**🎯 Made with ❤️ by the Developer Community**

[↑ Back to Top](#🚀-git--github-guide-master-commands-and-workflows) | [🤝 Contribute](#📝-how-to-contribute) | [🐛 Report Issues](https://github.com/sushantkumaryadav912/Git-GitHub-Guide/issues)

*Happy coding! 🚀*
