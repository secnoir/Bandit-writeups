# ⏱️ Bandit Level 21 → Level 22

## 🎯 Goal

Find the password for the next level.  
Hint: Look into the **cron jobs** running for `bandit22`.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit21`
- **Password:** _Use the password from Level 20_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit21

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220

2. Check cron jobs for bandit22

Cron job files for each user live in /etc/cron.d/.
Let’s look for one related to bandit22:

ls -l /etc/cron.d/

You should see something like: cronjob_bandit22
3. Inspect the cron job script

cat /etc/cron.d/cronjob_bandit22

Output example:

@reboot bandit22 /usr/bin/cronjob_bandit22.sh

Now read that script:

cat /usr/bin/cronjob_bandit22.sh

You’ll see that it copies a file to a temporary directory like this:

#!/bin/bash

myname=$(whoami)
mytarget="/tmp/$myname"
cat /etc/bandit_pass/bandit22 > $mytarget

4. Grab the password!

Since the script writes to /tmp/bandit22 on reboot or at regular intervals, just check:

cat /tmp/bandit22

💥 Boom — that’s your password for Level 22!
📚 What I Learned

    How to read and understand cron job scripts

    How temporary files can be used to pass secrets

    Real-world use of automation and system maintenance scripts

✅ Result

Password for Level 22 successfully retrieved!
