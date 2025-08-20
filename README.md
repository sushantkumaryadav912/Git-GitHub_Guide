# GitHub Commands Guide

## Repository Setup

### For any new repository
```bash
echo "# your-repo-name" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:username/repo-name.git
git push -u origin main
```

### For existing repo
```bash
git remote add origin git@github.com:username/repo-name.git
git branch -M main
git push -u origin main
```

## Cloning Repositories

### Clone a repository
```bash
git clone git@github.com:username/repo-name.git
# or with HTTPS
git clone https://github.com/username/repo-name.git
```

### Clone specific branch
```bash
git clone -b branch-name git@github.com:username/repo-name.git
```

### Clone with custom folder name
```bash
git clone git@github.com:username/repo-name.git custom-folder-name
```

## Basic Operations

### Check status
```bash
git status
```

### Add files
```bash
git add .                    # Add all files
git add filename.txt         # Add specific file
git add *.js                # Add all JS files
```

### Commit changes
```bash
git commit -m "commit message"
git commit -am "add and commit in one step"
```

### Push changes
```bash
git push                     # Push to current branch
git push origin main         # Push to specific branch
git push -u origin branch    # Push and set upstream
```

### Pull changes
```bash
git pull                     # Pull from current branch
git pull origin main         # Pull from specific branch
```

## Branch Management

### Create and switch branches
```bash
git branch branch-name       # Create branch
git checkout branch-name     # Switch to branch
git checkout -b branch-name  # Create and switch in one step
git switch branch-name       # Modern way to switch
git switch -c branch-name    # Modern way to create and switch
```

### List branches
```bash
git branch                   # Local branches
git branch -r               # Remote branches
git branch -a               # All branches
```

### Delete branches
```bash
git branch -d branch-name    # Delete local branch (safe)
git branch -D branch-name    # Force delete local branch
git push origin --delete branch-name  # Delete remote branch
```

### Merge branches
```bash
git checkout main
git merge feature-branch
```

## Handling Merge Conflicts

### When merge conflicts occur
1. Git will mark conflicted files
2. Open conflicted files and look for conflict markers:
```
<<<<<<< HEAD
Your current changes
=======
Incoming changes
>>>>>>> branch-name
```

### Resolve conflicts manually
```bash
# Edit files to resolve conflicts
git add resolved-file.txt
git commit -m "resolve merge conflict"
```

### Use merge tools
```bash
git mergetool               # Open configured merge tool
```

### Abort merge if needed
```bash
git merge --abort           # Cancel the merge
```

## Stashing Changes

### Save work temporarily
```bash
git stash                   # Stash current changes
git stash save "message"    # Stash with message
git stash list             # List all stashes
```

### Retrieve stashed work
```bash
git stash pop              # Apply and remove latest stash
git stash apply            # Apply without removing stash
git stash apply stash@{0}  # Apply specific stash
```

### Manage stashes
```bash
git stash drop stash@{0}   # Delete specific stash
git stash clear            # Delete all stashes
```

## Viewing History

### View commit history
```bash
git log                    # Full log
git log --oneline         # Compact log
git log --graph           # Visual graph
git log -n 5             # Last 5 commits
```

### View changes
```bash
git diff                  # Unstaged changes
git diff --staged         # Staged changes
git diff HEAD~1           # Changes since last commit
```

## Undoing Changes

### Unstage files
```bash
git reset filename.txt    # Unstage specific file
git reset                # Unstage all files
```

### Undo commits
```bash
git reset --soft HEAD~1   # Undo commit, keep changes staged
git reset --mixed HEAD~1  # Undo commit, keep changes unstaged
git reset --hard HEAD~1   # Undo commit, discard changes
```

### Revert commits
```bash
git revert commit-hash    # Create new commit that undoes changes
```

## Remote Management

### View remotes
```bash
git remote -v             # List all remotes
```

### Add/remove remotes
```bash
git remote add upstream git@github.com:original/repo.git
git remote remove upstream
```

### Fetch from remotes
```bash
git fetch origin          # Fetch from origin
git fetch --all          # Fetch from all remotes
```

## Tags

### Create tags
```bash
git tag v1.0.0            # Lightweight tag
git tag -a v1.0.0 -m "Version 1.0.0"  # Annotated tag
```

### Push tags
```bash
git push origin v1.0.0    # Push specific tag
git push --tags           # Push all tags
```

## GitHub Specific

### Fork workflow
```bash
# After forking on GitHub
git clone git@github.com:yourusername/forked-repo.git
git remote add upstream git@github.com:original/repo.git
git fetch upstream
git checkout main
git merge upstream/main
```

### Pull Request workflow
```bash
git checkout -b feature-branch
# Make changes
git add .
git commit -m "add new feature"
git push origin feature-branch
# Create PR on GitHub
```

## Useful Aliases

Add these to your `~/.gitconfig`:
```bash
[alias]
    co = checkout
    br = branch
    ci = commit
    st = status
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = !gitk
    ps = push
    pl = pull
    lg = log --oneline --graph --decorate --all
```

## Emergency Commands

### Reset to remote state
```bash
git fetch origin
git reset --hard origin/main  # WARNING: Loses local changes
```

### Clean untracked files
```bash
git clean -n              # Preview what will be deleted
git clean -fd             # Delete untracked files and directories
```

### Recover deleted branch
```bash
git reflog                # Find commit hash
git checkout -b recovered-branch commit-hash
```
