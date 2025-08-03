# 🗜️ Bandit Level 12 → Level 13

## 🧠 Goal

The password for the next level is hidden **within a file that has been compressed multiple times** (with different formats).  
The starting file is `/tmp/data.txt`.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit12`
- **Password:** _Use the password from Level 11_

---

## 🛠️ Steps to Solve

### 1. SSH into the server

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220

2. Copy the data file to your working directory

cp /tmp/data.txt ~
cd ~

3. Start inspecting the file type

file data.txt

Let’s say it says: gzip compressed data. So rename it and extract it.

mv data.txt data.gz
gunzip data.gz

4. Repeat the process

Every time you extract a file, check its type and use the right command:
Examples of what you may see:
File Type Output	What to Run
gzip	gunzip filename.gz
bzip2	bunzip2 filename.bz2
POSIX tar	tar -xf filename.tar
ASCII text	cat filename

You'll do this multiple times (about 9 times) until you finally get a plain-text password.
🔄 General loop (pseudo-code)

while true; do
  file *         # check the file type
  # rename if needed
  # extract it (gunzip, bunzip2, tar -xf, etc.)
done

✅ Final Output

Eventually, you'll be left with a plain-text file. Just open it:

cat finalfile

📌 That’s your password for Level 13.
📚 What I Learned

    How to identify and extract files in multiple compression formats

    Useful commands: file, gunzip, bunzip2, tar -xf, mv

    Basic scripting mindset for repetitive tasks

✅ Result

Password for Level 13 successfully retrieved!
