# 🚀 Bandit Level 31 → Level 32 (FINAL)

## 🎯 Goal

Create a Git repository **containing a file named `key.txt`**.  
The file must have the content:  
```text
May I come in?

Then, push the repo to the remote Bandit Git repo.
🖥️ Connection Details

    Host: bandit.labs.overthewire.org

    Port: 2220

    Username: bandit31

    Password: Use the password from Level 30

🛠️ Steps to Solve
1. SSH into Bandit31

ssh bandit31@bandit.labs.overthewire.org -p 2220

2. Create a temporary working directory

mkdir /tmp/irfan_repo
cd /tmp/irfan_repo

3. Initialize a Git repo and add key.txt

git init
echo "May I come in?" > key.txt
git add key.txt
git commit -m "Add key.txt"

4. Add remote and push

git remote add origin ssh://bandit31-git@localhost/home/bandit31-git/repo
git push origin master

    If main is your branch instead of master, push with:

    git push origin main

You may get asked for a password — enter Bandit31's password again.

🎉 If everything was correct, you'll be greeted with:

Well done. The password to the next level is ...

👏 You’ve completed all Bandit levels!
📚 What I Learned

    How to initialize and push a Git repository

    How to use Git over SSH

    How to work with Git programmatically for automation and challenges

✅ Result

You have completed Bandit from Level 0 → 32.

    The skills you’ve picked up here — Linux basics, permissions, Git internals, and SSH — are solid foundations for ethical hacking and CTF competitions.


