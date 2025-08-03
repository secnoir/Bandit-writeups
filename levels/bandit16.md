# 🔒 Bandit Level 15 → Level 16

## 🧠 Goal

The password for the next level can be retrieved by submitting the current password to **port 30001**, but this time using **SSL encryption**.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit15`
- **Password:** _Use the password from Level 14_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit15

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220

2. Submit the password via SSL

Use openssl s_client to connect securely to localhost on port 30001:

echo <CURRENT_PASSWORD> | openssl s_client -connect localhost:30001

    Replace <CURRENT_PASSWORD> with the password you got from Level 14.

✅ Example

echo p4ssw0rd123 | openssl s_client -connect localhost:30001

After a short SSL handshake, you’ll see output from the server — at the bottom, you’ll find the password for Level 16.
📚 What I Learned

    How to interact with SSL-enabled services using openssl

    Basics of encrypted client-server communication

    More real-world command-line security tooling

✅ Result

Password for Level 16 successfully retrieved!
