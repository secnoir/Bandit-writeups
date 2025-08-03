# 🟡 Bandit Level 1 → Level 2

## 🧠 Goal

The password for the next level is stored in a file called `-` (a single dash) located in the home directory. You need to figure out how to read this file.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit1`
- **Password:** _Use the password you got from Level 0_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220

Enter the password you got from Level 0.
2. List the files

ls -la

You’ll see a file named - in the directory. This is a tricky filename because - is interpreted as an option/flag by most commands.
3. Read the file using special syntax

To read a file named -, you can tell cat to treat the filename as input, not an option, by using ./ in front of it:

cat ./-

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to handle files with special names (like -)

    That ./ can be used to reference a file explicitly from the current directory

    That command-line tools interpret - as a flag unless you tell them otherwise

✅ Result

Successfully retrieved the password for Level 2.
