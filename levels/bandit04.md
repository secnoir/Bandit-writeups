# 🔵 Bandit Level 3 → Level 4

## 🧠 Goal

The password for the next level is stored in a file named **“inhere”** located inside the **`inhere/` directory**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit3`
- **Password:** _Use the password from Level 2_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220

2. Go into the inhere directory

cd inhere

3. List files in the directory

ls

You’ll see a file named -file00 (or something similar).
4. Use cat to read the file with the password

cat .hidden

Oops — that was Level 2 😄

Now for real:

cat ./file

(If the file name is something like -file00, remember to prefix with ./ to avoid confusion with flags.)

Example:

cat ./-file00

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to navigate into directories using cd

    How to list directory contents with ls

    How to read files with special characters using ./

    That challenges often test basic navigation and reading skills

✅ Result

Password for Level 4 successfully retrieved
