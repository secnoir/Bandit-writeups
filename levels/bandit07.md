# ⚪ Bandit Level 6 → Level 7

## 🧠 Goal

The password for the next level is stored **somewhere on the server** in a **file that**:

- Is **owned by user** `bandit7`
- Is **owned by group** `bandit6`
- Is **33 bytes** in size

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit6`
- **Password:** _Use the password from Level 5_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220

2. Use the find command

Run this from the root directory to search the whole system:

find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null

    ⚙️ Explanation:

        / = search entire filesystem

        -type f = look for files only

        -user bandit7 = must be owned by user bandit7

        -group bandit6 = must be owned by group bandit6

        -size 33c = exactly 33 bytes

        2>/dev/null = hides permission denied errors

You'll get an output like:

/some/long/path/to/file

3. Read the file

Use cat to read it:

cat /some/long/path/to/file

Output:

<REDACTED_PASSWORD>

📚 What I Learned

    How to use the find command to locate files by:

        User ownership

        Group ownership

        Exact size

    How to suppress errors with 2>/dev/null

    That root-level searching is powerful but noisy

✅ Result

Password for Level 7 successfully retrieved!
