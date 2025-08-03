# 🔁 Bandit Level 11 → Level 12

## 🧠 Goal

The password for the next level is stored in `data.txt`, but the text has been **encoded using ROT13**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit11`
- **Password:** _Use the password from Level 10_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220

2. View the encoded file

cat data.txt

The output will look like gibberish — that’s ROT13. Example:

Guvf vf zl frperg cnffjbeq

3. Decode it using tr

ROT13 shifts letters 13 places, so use tr like this:

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

This will output:

This is my secret password

🎯 And there’s your password.
📚 What I Learned

    How ROT13 encoding works (shifts letters 13 places)

    How to decode ROT13 using tr (translate)

    Basic command chaining with pipes

✅ Result

Password for Level 12 successfully retrieved!
