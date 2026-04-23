# 🚀 GitHub SSH Setup Guide (MacBook)

This guide explains how to connect your GitHub account to your laptop terminal using SSH, create files, and upload them to a repository. Perfect for DevOps/Platform Ops practice.

---

## 1️⃣ Configure Git with Your GitHub Account
Run these commands once on your laptop:
```bash
git config --global user.name "YourGitHubUsername"
git config --global user.email "your-email@example.com"

👉 Use the same email you registered on GitHub.
---
2️⃣ Create or Go to Your Project Folder
cd ~/path/to/your/project

Example:
cd ~/Movies/Thinker\ TechSutra\ Marathi/DevOps/github

---
3️⃣ Initialize Git Repository
git init

👉 This creates a hidden .git folder.
---
4️⃣ Generate SSH Key (Permanent Setup)
ssh-keygen -t ed25519 -C "your-email@example.com"

Press Enter for default location (~/.ssh/id_ed25519).
Set a passphrase (optional).
---
5️⃣ Start SSH Agent & Add Key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

---
6️⃣ Copy Public Key
cat ~/.ssh/id_ed25519.pub

👉 Copy the entire output (starts with ssh-ed25519 ...).
---
7️⃣ Add SSH Key to GitHub
Go to GitHub → Settings → SSH and GPG keys → New SSH key.
Paste the copied key.
Save.
---
8️⃣ Connect Local Repo to GitHub (SSH URL)
git remote add origin git@github.com:ThinkerOnlineHub/git-github-mastery.git

Check connection:
git remote -v

---
9️⃣ Create and Commit a File
Example: README.md
echo "# Git & GitHub Mastery" > README.md
git add README.md
git commit -m "Add README.md file"

---
🔟 Push Code to GitHub
git branch -M main
git push -u origin main

👉 Now your file is uploaded without asking for username/password.
---
1️⃣1️⃣ Add Screenshots Folder Later
mkdir screenshots
cp ~/Desktop/screenshot1.png screenshots/
git add screenshots/
git commit -m "Add screenshots folder"
git push

---
✅ Summary
Configure Git with your username/email.
Generate SSH key once, add it to GitHub.
Use SSH remote URL (git@github.com:...) for permanent access.
Add/commit/push files or folders anytime.
---
💡 With this setup, you’ll never face password errors again. Your MacBook is permanently linked to GitHub via SSH — ideal for DevOps practice and building your Platform Ops Engineer workflow.

---

👉 Save this as **`GitHub-SSH-Setup.md`** in your repo. It becomes your personal reference guide and also helps others who want to learn.  

Do you want me to also create a **second Markdown template** for “Daily Git Practice Notes” (where you log each command you learn), so your repo doubles as a learning journal?
