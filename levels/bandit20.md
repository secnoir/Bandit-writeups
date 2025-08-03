# 🛠️ Bandit Level 19 → Level 20

## 🎯 Goal

There’s a script that runs with elevated permissions (as `bandit20`) when executed.  
Your task: **modify the script to reveal the password for Level 20**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit19`
- **Password:** _Use the password from Level 18_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit19

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220

2. Look for the script

ls -l

You'll find a script called bandit20-do.

Check its permissions:

ls -l ./bandit20-do

You’ll notice it has the SUID bit set — it runs as bandit20.
3. Understand how to use it

Run it to see what it expects:

./bandit20-do

Output:

Run a command as another user.
Usage: ./bandit20-do <command>

Nice — it runs any command as bandit20!
4. Use it to read the next password

You now have a way to run commands as bandit20, so let’s just cat the password file:

./bandit20-do cat /etc/bandit_pass/bandit20

🎉 That prints the password for Level 20.
📚 What I Learned

    What the SUID (Set User ID) bit does

    How to run commands as another user securely

    How scripts can be abused when given elevated access

✅ Result

Password for Level 20 successfully retrieved!
