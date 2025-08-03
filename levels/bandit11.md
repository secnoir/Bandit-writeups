# 🧵 Bandit Level 10 → Level 11

## 🧠 Goal

The password for the next level is stored in the file `data.txt`, which contains a **Base64-encoded** string.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit10`
- **Password:** _Use the password from Level 9_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220

2. Confirm data.txt is there

ls

3. Read the contents

cat data.txt

You’ll see a long scrambled-looking string — that’s Base64.
4. Decode the string using base64 -d

cat data.txt | base64 -d

Output:

<REDACTED_PASSWORD>

    ✅ -d tells base64 to decode.

📚 What I Learned

    How to identify a Base64-encoded string

    How to decode it using base64 -d

    The value of piping commands (cat → base64)

✅ Result

Password for Level 11 successfully retrieved!
