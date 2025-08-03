# 🟢 Bandit Level 0 → Level 1

## 🧠 Goal

Retrieve the password for **Level 1** by logging into the server as `bandit0` and reading a file called `readme` located in the home directory.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit0`
- **Password:** `bandit0`

---

## 🛠️ Steps to Solve

### 1. SSH into the server
Use the `ssh` command to connect to the Bandit server:
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

    💡 If this is your first time connecting, type yes when asked about the authenticity of the host.

2. List the files in the home directory

ls

Output:

readme

3. Read the file to find the password

cat readme

Output:

<REDACTED_PASSWORD>

    🔐 Do not share the actual password. Just note that you found it successfully.

📚 What I Learned

    How to use ssh to log into a remote Linux server

    How to list files with ls

    How to read a file with cat

    That the Bandit challenges build Linux terminal confidence one step at a time

✅ Result

I successfully retrieved the password for Level 1, and I'm ready to move on to the next challenge.
