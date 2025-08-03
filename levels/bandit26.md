# 🔐 Bandit Level 25 → Level 26

## 🎯 Goal

Use the provided **SSH private key** to log in as `bandit26` and retrieve the password for the next level.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit25`
- **Password:** _Use the password from Level 24_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit25

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220

2. Locate the private SSH key

ls

You’ll see a file:

sshkey.private

This key lets you SSH into the next level without a password.
3. Use the key to login as bandit26

From your local terminal (or using ssh -i inside Bandit25 if allowed):

ssh -i sshkey.private bandit26@bandit.labs.overthewire.org -p 2220

    If you get a permissions warning, you can run:

    chmod 600 sshkey.private

✅ You should now be logged in as bandit26.
4. Get the password

cat /etc/bandit_pass/bandit26

That’s your password for the next level!
📚 What I Learned

    How SSH key-based authentication works

    How to use ssh -i to log in with a private key

    Why key permissions are important (must be 600)

✅ Result

Password for Level 26 successfully retrieved!
