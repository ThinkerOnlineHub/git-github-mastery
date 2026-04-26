# Day-13: Git Branching, Merge & Conflict Resolution (Real-World Practice)

## 📌 Goal
To simulate a real developer workflow using Git branching, perform merges, handle conflicts, and resolve common Git issues faced in real DevOps environments.

---

## 🧠 Concept Explanation

In real-world development:

- `main` → stable production branch  
- `feature/*` → used for new work  
- Developers NEVER work directly on `main`

👉 Safe workflow:
```
main → feature branch → changes → merge → main
```

---

## 🌿 Why Branching is Important

- Prevents breaking production code
- Enables parallel development
- Supports team collaboration
- Required for CI/CD pipelines

---

## 🛠️ Hands-on Implementation

---

### 🔹 Step 1: Create Feature Branch

```bash
git branch feature/day-13-branching
git checkout feature/day-13-branching
```

---

### 🔹 Step 2: Make Changes

```bash
echo "Feature branch change" >> day-13.md
git add .
git commit -m "Feature update"
```

---

### 🔹 Step 3: Switch to Main

```bash
git checkout main
```

---

### 🔹 Step 4: Make Change in Main (Simulate Conflict)

```bash
echo "Main branch change" >> day-13.md
git add .
git commit -m "Main update"
```

---

### 🔹 Step 5: Merge Feature Branch

```bash
git merge feature/day-13-branching
```

---

## ⚠️ Real Error: Merge Conflict

### ❌ Error Output

```
CONFLICT (content): Merge conflict in day-13.md
Automatic merge failed
```

---

### 🧠 Why This Happens

- Same file modified in both branches
- Git cannot decide which change to keep

---

### 🔍 Conflict File Example

```
<<<<<<< HEAD
Main branch change
=======
Feature branch change
>>>>>>> feature/day-13-branching
```

---

### ✅ Fix Conflict

Edit file to:

```
Main branch change
Feature branch change
```

Then run:

```bash
git add .
git commit -m "Resolved merge conflict"
```

---

## Real time command output terminal screenshots 📸 In Screenshots directory

- Branch creation
- Merge conflict
- Conflict markers
- Conflict resolution

---

## ⚠️ Real-World Issue: Multiple Git Repositories

### ❌ Problem

- Two folders:
  - `Git-Github` (main repo)
  - `github/` (separate repo)

Git treated `github/` as external → caused errors like:

```
pathspec 'github' did not match any files
```

---

### 🧠 Root Cause

Mixing two repositories in one workflow

---

### ✅ Fix

- Work only inside main repo:
```bash
cd ~/DevOps/Git-Github
```

- Ignore external repo:

```bash
echo "github/" >> .gitignore
git add .gitignore
git commit -m "Ignore external repo"
```

---

## ⚠️ Real-World Issue: .DS_Store & Junk Files

### ❌ Problem

- macOS creates `.DS_Store`
- Causes unnecessary Git changes

---

### ✅ Fix (.gitignore)

```bash
echo ".DS_Store" >> .gitignore
git add .gitignore
git commit -m "Ignore system files"
```

---

## ⚠️ Real Error: Push Rejected (Fetch First)

```
! [rejected] main -> main (fetch first)
```

---

### 🧠 Cause

- Remote repo has commits not present locally

---

### ✅ Fix

```bash
git stash
git pull origin main --rebase
git push -u origin main
```

---

## ⚠️ Real Error: Unstaged Changes Blocking Rebase

### ❌ Cause

- Files like `.DS_Store` or `github/` not committed

---

### ✅ Fix

```bash
git restore .DS_Store
git stash
git pull origin main --rebase
```

---

## 🖼️ Upload Screenshots to GitHub

### Workflow

```bash
cp ~/Desktop/screenshot.png screenshots/
cd ~/DevOps/Git-Github

git add screenshots/
git commit -m "Add screenshots for Day-13"
git push
```

---

## 📊 Commands Summary

| Command | Purpose |
|--------|--------|
| git branch | List/create branches |
| git checkout | Switch branch |
| git merge | Merge branches |
| git stash | Temporarily save changes |
| git pull --rebase | Sync cleanly |
| git push | Upload to GitHub |

---

## 🚀 Why This Matters for DevOps

- Teams use feature branches for development
- Conflicts happen frequently in real projects
- Clean Git workflow is required for CI/CD
- Debugging Git issues is a daily responsibility

---

## 📝 Commit Message

```
Day-13: Implemented branching workflow, resolved merge conflicts, and handled real Git errors
```

---

## 🎯 Key Learnings

- Feature branching workflow
- Merge conflict resolution
- Handling multiple repositories
- Using .gitignore effectively
- Fixing push and rebase issues

---

## 💡 Reflection

This was a real-world simulation of developer workflow.

I not only:
- Created branches
- Merged changes

…but also:
- Faced real Git errors
- Understood root causes
- Applied production-level fixes

This significantly improved my confidence in handling Git in collaborative environments.

---

## ⏭️ Next Step

Learn:

```bash
git rebase
git stash
git cherry-pick
```

---

## ✅ End of Day-13
