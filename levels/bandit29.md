# 🕵️ Bandit Level 28 → Level 29

## 🎯 Goal

You’ve cloned a Git repo again — but this time, the password is not in the current files.  
Hint: It was once there… but got removed. 🧹

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit28`
- **Password:** _Use the password from Level 27_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit28

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220

2. Clone the Git repo

git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
cd repo

3. Check the latest commit

git log

You’ll see one or more commits — look at the commit hash(es).
Now inspect earlier commits using:

git checkout <commit_hash>

Or simply show diffs:

git log -p

Scroll through until you find something like:

- password: some_secret_password_here

🎉 That's the password for Level 29!
Optional: View a specific file from an old commit

git show <commit_hash>:<filename>

For example:

git show a1b2c3d4e5f6:README

📚 What I Learned

    How to explore Git commit history with git log and git show

    That Git stores all file changes (even deleted ones!)

    How to recover deleted secrets from version control

✅ Result

Password for Level 29 successfully retrieved!
