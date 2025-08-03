# 🔴 Bandit Level 9 → Level 10

## 🧠 Goal

The password for the next level is stored in a file called `data.txt`. It is the **only line** that matches a **pattern of exactly 1 occurrence of a lowercase letter followed by 2 uppercase letters**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit9`
- **Password:** _Use the password from Level 8_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220

2. Confirm the file is present

ls

You'll see:

data.txt

3. Use grep with regex to extract the password pattern

grep -E '[^a-zA-Z][a-z][A-Z]{2}[^a-zA-Z]' data.txt

This finds lines containing a lowercase letter followed by 2 uppercase letters, surrounded by non-letters (so we don’t catch longer patterns).

Optional: To extract just the match, you could refine this using grep -o, cut, or awk, but for this level just spotting the correct line is enough.
📚 What I Learned

    Basics of regular expressions:

        [a-z] = lowercase letter

        [A-Z]{2} = two uppercase letters

        [^a-zA-Z] = non-letter characters (to isolate the pattern)

    That grep -E enables extended regex (similar to egrep)

✅ Result

Password for Level 10 successfully retrieved!
