# 🧬 Bandit Level 24 → Level 25

## 🎯 Goal

Find the password for the next level.  
You’re given a binary called `bandit24`. It stores the password in memory and compares it against your input.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit24`
- **Password:** _Use the password from Level 23_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit24

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220

2. List files

ls

You’ll see:

bandit24

3. Run the binary

./bandit24

It’ll ask for a password. Try entering something random:

Wrong!

4. Use ltrace to inspect library calls

Let’s trace the program:

ltrace ./bandit24

Example output:

__libc_start_main(0x8048520, 1, 0xffffd754, 0x80485e0 <unfinished ...>
strcmp("s3cr3tpass", "your_input") = 1
puts("Wrong!"...)
Wrong!

💥 ltrace exposes the password in the first strcmp() call. It’s the first string argument!
5. Use that password

Now just re-run the binary and enter the correct password:

./bandit24
# Enter: s3cr3tpass (whatever you saw in ltrace)

It will output the password for Bandit25.
📚 What I Learned

    How ltrace can be used to extract secrets from binaries

    How library calls like strcmp() can expose hidden logic

    A basic example of binary reverse engineering

✅ Result

Password for Level 25 successfully retrieved!
