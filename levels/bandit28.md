# 📁 Bandit Level 27 → Level 28

## 🎯 Goal

Clone a Git repository containing the password for the next level.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit27`
- **Password:** _Use the password from Level 26_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit27

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220

2. Clone the Git repository

git clone ssh://bandit27-git@localhost/home/bandit27-git/repo

If prompted for a password, use the same one as this level.
3. Enter the cloned repo

cd repo

4. List the files

ls -la

You should see a file like:

README

Let’s read it:

cat README

✅ Boom! That’s the password for Bandit28!
📚 What I Learned

    How to clone private Git repositories over SSH

    How Git repositories can store sensitive data

    That .git folders contain full commit history

✅ Result

Password for Level 28 successfully retrieved!
