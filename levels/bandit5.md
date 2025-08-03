# 🟣 Bandit Level 4 → Level 5

## 🧠 Goal

The password for the next level is stored in **the only human-readable file** in the **`inhere/`** directory. All others are either binary or empty.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit4`
- **Password:** _Use the password from Level 3_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220

2. Go into the inhere directory

cd inhere

3. Check the file types

List all files with detailed info:

ls -la

Then use the file command on each one:

file ./*

You’ll see output like:

./-file00: data
./-file01: ASCII text
./-file02: empty
...

Look for the file that says ASCII text.
4. Read the human-readable file

Example:

cat ./-file01

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to use the file command to determine a file's type

    How to differentiate between binary, empty, and text files

    That the correct file may not be obvious from name alone — file content/type matters

✅ Result

Retrieved the password for Level 5 successfully.
