# 🧩 Bandit Level 26 → Level 27

## 🎯 Goal

The password for the next level is **retrieved by running a command on login** using a **special SSH key** — but you can't run arbitrary commands.

You must bypass a limited `command="..."` restriction in `authorized_keys`.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit26`
- **Password:** _Use the password from Level 25_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit26

```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220

2. Check the home directory

ls -la

You’ll see:

bandit27-do
sshkey.private

The bandit27-do binary is the key here — it executes commands as the bandit27 user.
3. Use the bandit27-do binary

Let’s try running a simple command as bandit27:

./bandit27-do whoami

Output:

bandit27

Great! Now let’s use it to read the password file:

./bandit27-do cat /etc/bandit_pass/bandit27

🎉 That’s your password for Level 27!
📚 What I Learned

    How command="..." in authorized_keys restricts SSH key use

    How binaries like bandit27-do can be used for privilege escalation

    Executing specific commands as another user securely

✅ Result

Password for Level 27 successfully retrieved!
