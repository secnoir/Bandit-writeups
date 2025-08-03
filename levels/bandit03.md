# 🟠 Bandit Level 2 → Level 3

## 🧠 Goal

The password for the next level is stored in a **hidden file** in the home directory.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit2`
- **Password:** _Use the password you got from Level 1_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220

Enter the password retrieved from Level 1.
2. List all files, including hidden ones

Regular ls won’t show hidden files, so use -a:

ls -la

You’ll see a file like:

.rQe8h7sY... (name may vary)

The dot (.) at the beginning makes it a hidden file.
3. Read the hidden file

Use cat to read the file:

cat .hidden

(Replace .hidden with the actual hidden filename you see if it’s different.)

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to view hidden files with ls -a

    Why files starting with . are hidden by default in Unix/Linux

    That ls and cat are powerful tools for file discovery and reading

✅ Result

Successfully retrieved the password for Level 3.
