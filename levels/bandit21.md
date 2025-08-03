# 📡 Bandit Level 20 → Level 21

## 🎯 Goal

There's a program that connects to a **custom port** on localhost and expects to receive a specific reply before it sends back the password.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit20`
- **Password:** _Use the password from Level 19_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit20

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220

2. Explore the files

ls

You’ll see a file called suconnect — this is the program that will connect to your listener.
3. Run a listener on a port (e.g. 12345)

We’ll use nc (netcat) to listen and automatically respond:

echo "YES" | nc -l -p 12345

    This listens on port 12345 and responds with "YES" when a client connects.

4. In another terminal, run the suconnect program

Open a new terminal and SSH in again:

ssh bandit20@bandit.labs.overthewire.org -p 2220

Then run:

./suconnect 12345

This connects to port 12345, waits for the response (YES), and then sends back the password.

You’ll see it in your first terminal (where nc is running).
✅ Full Steps (Quick Version)

Terminal 1:

ssh bandit20@bandit.labs.overthewire.org -p 2220
echo "YES" | nc -l -p 12345

Terminal 2:

ssh bandit20@bandit.labs.overthewire.org -p 2220
./suconnect 12345

✅ The password will show up in Terminal 1!
📚 What I Learned

    How to use nc (netcat) to set up basic TCP listeners

    How to automate client/server interactions with scripts

    Real-world socket communication basics

✅ Result

Password for Level 21 successfully retrieved!
