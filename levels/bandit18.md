# 🕵️‍♂️ Bandit Level 17 → Level 18

## 🎯 Goal

The password for the next level is stored in a file **readable by user `bandit18`**, but **it gets deleted immediately** after you log in.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit17`
- **Password:** _Use the password from Level 16_

---

## 🛠️ Steps to Solve

### 1. Create a temp shell that pauses before deletion

To capture the password **before the login script deletes it**, we’ll use an alternate shell:

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220 -t "bash --noprofile"

    -t forces pseudo-terminal allocation
    --noprofile skips the normal login scripts (including the one that deletes the file)

2. Look in /tmp for the file

Once logged in, you can search for where the password might be saved temporarily. Try this:

ls /tmp

Look for a folder named something like bandit18.... If you see one, list its contents:

ls -la /tmp/bandit18*

You should find a file like password.
3. Read the file before it disappears!

cat /tmp/bandit18*/password

And just like that — 💥 — you'll have the password!
📚 What I Learned

    How to bypass login scripts using bash --noprofile

    How temp files can be manipulated or deleted in automated environments

    How to think creatively under constraints

✅ Result

Password for Level 18 successfully retrieved!
