# Day-11: Git Basics & GitHub Integration (CLI Hands-on)

## 📌 Goal
To implement Git fundamentals using CLI and successfully connect a local repository to GitHub, while resolving real-world errors during the process.

---

## 🧠 Concept Overview

Git is a **version control system**, and GitHub is a **remote repository platform**.

👉 Workflow:
```
Local (Laptop) → Git → GitHub (Remote)
```

- `git commit` → saves locally  
- `git push` → uploads to GitHub  
- `git pull` → syncs remote changes  

---

## 🛠️ Step-by-Step Implementation

### 🔹 Step 1: Initialize Repository
```bash
git init
git status
```

✔ Repository initialized with `main` branch

---

### 🔹 Step 2: Add & Commit Files
```bash
git add .
git commit -m "Initiate commit - DevOps learning day 1"
```

✔ Files committed locally

---

### 🔹 Step 3: Connect to GitHub
```bash
git remote add origin git@github.com:thinkeronlinehub/git-github-mastery.git
git remote -v
```

✔ Remote repository linked

---

## ⚠️ Real Errors Faced & Fixes

---

### ❌ Error 1: Wrong Branch Name

```bash
git pull origin mail --rebase
```

**Error:**
```
fatal: couldn't find remote ref mail
```

### ✅ Fix:
```bash
git pull origin main --rebase
```

📌 Cause: Typo (`mail` instead of `main`)

---

### ❌ Error 2: Push Rejected (Fetch First)

```bash
git push -u origin main
```

**Error:**
```
! [rejected] main -> main (fetch first)
```

### 🧠 Why This Happened

- GitHub repo already had commits (README, etc.)
- Local repo had different history
- Git prevented overwrite

---

### ✅ Solution (Recommended)

```bash
git checkout main
git pull origin main --rebase
git push -u origin main
```

✔ Successfully synced local + remote

---

### ❌ Error 3: Remote Contains Work

**Problem:**
Push rejected again due to mismatch

### ✅ Fix Options

#### ✔ Safe Option:
```bash
git pull origin main --rebase
git push
```

#### ⚠️ Risky Option:
```bash
git push --force
```

---

### ❌ Error 4: Embedded Repository Warning

```
warning: adding embedded git repository: github
```

### 🧠 Cause:
Nested Git repo inside project

### ✅ Fix:
```bash
git rm --cached github
```

---

## 📊 Final Workflow

```bash
git status
git add .
git commit -m "message"
git push
```

---

## 🚀 Key Learnings

- Git commits are **local**
- GitHub stores **remote version**
- Always **pull before push**
- Small mistakes (like branch name) cause errors
- Debugging Git is a critical DevOps skill

---

## 🖼️ Screenshots

📸 Attached:
- Initial git setup
- Commit creation
- Push rejection
- Rebase fix
- Successful push

---

## 📝 Commit Message

```
Day-11: Git basics, resolved push conflict, and integrated GitHub using CLI
```

---

## 🔐 Important Security Fix

Accidentally committed:
```
techsutra_key.pem
```

### ❌ Sensitive file (private key)

### ✅ Fix:
```bash
echo "*.pem" >> .gitignore
git rm --cached techsutra_key.pem
git commit -m "Removed sensitive file"
git push
```

---

## 🎯 Outcome

✅ Successfully:
- Initialized Git repo  
- Created commits  
- Connected to GitHub  
- Resolved real errors  
- Pushed code successfully  

---

## 💡 Reflection

This was a practical Git learning session where I:
- Faced real errors
- Understood root causes
- Applied correct fixes

This improved my confidence in handling Git workflows in real DevOps environments.

---

## ⏭️ Next Step

Learn:
```bash
git log
git diff
git branch
git checkout
```

---

## ✅ End of Day-11
