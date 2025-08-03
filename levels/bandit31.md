# 🌿 Bandit Level 30 → Level 31

## 🎯 Goal

Find the password for the next level hidden inside a **branch** of a Git repository.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit30`
- **Password:** _Use the password from Level 29_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit30

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220

2. Clone the Git repository

git clone ssh://bandit30-git@localhost/home/bandit30-git/repo
cd repo

3. List all branches

git branch -a

You’ll likely see:

remotes/origin/secret

4. Check out the secret branch

git checkout secret

5. List and read files

ls
cat README

🎉 Inside the README, you'll find the password for Level 31!
📚 What I Learned

    How to list and switch to remote Git branches

    That Git can store sensitive data across different branches

    How to access non-default branches with git checkout

✅ Result

Password for Level 31 successfully retrieved!
