# 📡 Bandit Level 14 → Level 15

## 🧠 Goal

The password for the next level can be retrieved by **submitting the current password to a specific port on localhost (127.0.0.1)**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit14`
- **Password:** _Use the password from Level 13_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220

2. Use nc to connect to the local service

echo <CURRENT_PASSWORD> | nc localhost 30000

    Replace <CURRENT_PASSWORD> with the password from Level 13.

✅ Example

echo s0m3p@ssw0rd | nc localhost 30000

You’ll get back the password for Level 15 printed in the terminal.
📚 What I Learned

    How to use nc (netcat) to interact with TCP services

    How to pipe data into commands using echo

    Basics of local network communication on ports

✅ Result

Password for Level 15 successfully retrieved!
