# 🔑 Bandit Level 13 → Level 14

## 🧠 Goal

The password for the next level is stored in the **file `/etc/bandit_pass/bandit14`** and can **only be read by user `bandit14`**.  
You’re given a **private SSH key** for that user.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit13`
- **Password:** _Use the password from Level 12_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit13

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220

2. Look for the private key file

ls

You’ll see:

sshkey.private

3. Set correct permissions

Private key files must have read-only permissions, or SSH won’t accept them:

chmod 600 sshkey.private

4. SSH into bandit14 using the key

Now use the private key to log in as bandit14:

ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

You’ll now be inside the bandit14 shell!
5. Read the password

cat /etc/bandit_pass/bandit14

🎉 You’ve got the password for Level 14!
📚 What I Learned

    How to use SSH with a private key (ssh -i keyfile user@host)

    Importance of setting key permissions to 600

    How to log in as another user using only a key (no password)

✅ Result

Password for Level 14 successfully retrieved!
