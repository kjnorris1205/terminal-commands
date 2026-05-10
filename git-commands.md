# Git Commands for Beginners

A simple guide to the most common Git commands you'll use every day.

---

## Setting Up Git (First Time Only)

Tell Git who you are before you start:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## Starting a Project

### Create a new local repository
```bash
git init
```

### Copy an existing repository from GitHub
```bash
git clone https://github.com/username/repository-name.git
```

---

## Checking Status

### See what files have changed
```bash
git status
```

### See the exact lines that changed
```bash
git diff
```

---

## Saving Your Changes (The Core Workflow)

This is the most common thing you'll do in Git:

### 1. Stage your changes (tell Git which files to save)
```bash
git add filename.txt        # stage a specific file
git add .                   # stage ALL changed files
```

### 2. Commit your changes (save a snapshot with a message)
```bash
git commit -m "Describe what you changed"
```

> **Tip:** Write short, clear commit messages like `"Fix login bug"` or `"Add homepage design"`.

---

## Working with GitHub (Remote)

### Check which remote repository is connected
```bash
git remote -v
```

### Download changes from GitHub (without merging)
```bash
git fetch
```

### Download AND merge changes from GitHub
```bash
git pull
```

### Upload your commits to GitHub
```bash
git push
```

> **Tip:** The typical daily flow is: `pull` → make changes → `add` → `commit` → `push`

---

## Branches

Branches let you work on new features without breaking the main code.

### See all branches
```bash
git branch
```

### Create a new branch
```bash
git branch feature-name
```

### Switch to a branch
```bash
git checkout feature-name
```

### Create AND switch to a new branch (shortcut)
```bash
git checkout -b feature-name
```

### Merge a branch into your current branch
```bash
git merge feature-name
```

### Delete a branch (after merging)
```bash
git branch -d feature-name
```

---

## Viewing History

### See past commits
```bash
git log
```

### See a compact one-line summary of commits
```bash
git log --oneline
```

---

## Undoing Mistakes

### Unstage a file (undo `git add`)
```bash
git restore --staged filename.txt
```

### Discard changes to a file (revert to last commit)
```bash
git restore filename.txt
```

### Undo the last commit (keeps your file changes)
```bash
git reset --soft HEAD~1
```

---

## Quick Reference

| Task | Command |
|---|---|
| Initialize a repo | `git init` |
| Clone a repo | `git clone <url>` |
| Check status | `git status` |
| Stage all changes | `git add .` |
| Commit changes | `git commit -m "message"` |
| Push to GitHub | `git push` |
| Pull from GitHub | `git pull` |
| Create & switch branch | `git checkout -b name` |
| View commit history | `git log --oneline` |
