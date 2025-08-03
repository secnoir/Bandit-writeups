# 🟡 Bandit Level 8 → Level 9

## 🧠 Goal

The password for the next level is stored in the **only line** of `data.txt` that occurs **only once**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit8`
- **Password:** _Use the password from Level 7_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220

2. Confirm the file exists

ls

Output:

data.txt

3. Sort the file and filter unique lines

Use sort and uniq -u to find the line that appears only once:

sort data.txt | uniq -u

This returns:

<REDACTED_PASSWORD>

📚 What I Learned

    sort is needed because uniq only detects duplicates next to each other

    uniq -u filters and prints only unique (non-duplicate) lines

    Combining tools like sort + uniq is a powerful Linux pattern

✅ Result

Password for Level 9 successfully retrieved!
