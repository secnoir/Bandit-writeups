# 🧠 Bandit Level 16 → Level 17

## 🎯 Goal

The password for the next level is stored on a **port listening on localhost (127.0.0.1)** but only accessible **if your connection comes from localhost** itself.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit16`
- **Password:** _Use the password from Level 15_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit16

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220

2. Check the script available

There’s a helpful script placed in /etc/bandit_pass/bandit17.

But first, list what’s in the current user's home dir:

ls

You’ll likely find a script named bandit18-do — this is a setuid binary that executes commands as bandit17.
3. Use ncat (or similar) to connect from localhost

The trick:
You need to connect as if you're on localhost. So you’ll use the bandit17 user via the bandit17-do helper and execute nc 127.0.0.1 30002 from their user context:

./bandit17-do cat /etc/bandit_pass/bandit17

Boom — that prints the password.

Why does this work?
You’re using a binary that runs as bandit17, which has permission to read the password file.
📚 What I Learned

    How to use setuid binaries to run commands as another user

    Understanding user-level privilege boundaries

    More scripting logic with secure local access

✅ Result

Password for Level 17 successfully retrieved!
