# 🟢 Bandit Level 7 → Level 8

## 🧠 Goal

The password for the next level is stored **in a file** called `data.txt`, and the file **contains the word “millionth”** on the line with the password.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit7`
- **Password:** _Use the password from Level 6_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220

2. Locate and inspect the file

ls

You’ll see:

data.txt

3. Use grep to search for the keyword

grep millionth data.txt

Output:

millionth  <REDACTED_PASSWORD>

This line contains the password you're looking for.
📚 What I Learned

    How to search for a specific string in a file using grep

    That grep <keyword> <file> is a fast way to locate matching lines

    Practical pattern matching for text processing

✅ Result

Password for Level 8 successfully retrieved!
