# 🟤 Bandit Level 5 → Level 6

## 🧠 Goal

Find the file in the **`inhere/`** directory that:

- Is **human-readable**
- Is **1033 bytes** in size
- Is **not executable**
- Is **only readable by the user (bandit5)**

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit5`
- **Password:** _Use the password from Level 4_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220

2. Navigate to the inhere/ directory

cd inhere

3. Use ls -l to inspect permissions and file sizes

ls -l

You're looking for a file that:

    Has 1033 bytes

    Has permission: -r-- (read-only for owner)

    Is not executable

Example output:

-r--r----- 1 bandit5 bandit5 1033 Jan 1 12:00 -file07

4. Verify the file type (optional)

file ./-file07

Make sure it says: ASCII text
5. Read the file

cat ./-file07

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to interpret file permissions (rwx)

    How to filter files by size and type

    That not all files in a directory are relevant — filters matter

✅ Result

Password for Level 6 successfully retrieved!
