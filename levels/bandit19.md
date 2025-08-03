# 🌀 Bandit Level 18 → Level 19

## 🎯 Goal

The password for the next level is stored in a **file read by a non-interactive shell**, and the shell immediately logs you out.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit18`
- **Password:** _Use the password from Level 17_

---

## 🛠️ Steps to Solve

### ❌ Problem

Trying to SSH normally will instantly kick you out:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220

Output:

Byebye!
Connection closed.

✅ Workaround: Provide a command with ssh

Instead of trying to open a shell, pass a command directly:

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat /home/bandit18/.bashrc

That works — and proves you can run commands remotely, even without an interactive shell.

Now use it to read the password file:

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat /etc/bandit_pass/bandit19

✅ You’ll get the password for Level 19 printed to your screen.
📚 What I Learned

    That non-interactive shells can restrict user access

    How to run single remote commands via SSH

    How to bypass logout scripts using command injection in SSH

✅ Result

Password for Level 19 successfully retrieved!
