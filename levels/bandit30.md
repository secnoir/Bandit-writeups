# 🏷️ Bandit Level 29 → Level 30

## 🎯 Goal

The password is stored in a **Git tag** in a remote repository.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit29`
- **Password:** _Use the password from Level 28_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit29

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220

2. Clone the Git repository

git clone ssh://bandit29-git@localhost/home/bandit29-git/repo
cd repo

3. List all tags in the repo

git tag

You’ll see something like:

secret

4. View the contents of the tag

git show secret

You should see:

<commit hash>
<other metadata>
Password: <your_password_here>

🎯 That’s the password for Level 30!
📚 What I Learned

    How to list Git tags with git tag

    How to inspect a tag with git show

    That Git tags can be used to hide or reference important information

✅ Result

Password for Level 30 successfully retrieved!
