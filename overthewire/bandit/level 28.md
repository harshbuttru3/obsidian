## Objective : 
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Solution : 
The password for next level is "4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7"

commands to get the password : 
```bash
cd /tmp
mkdir bandit28repo && cd bandit28repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit28-git@localhost/home/bandit28-git/repo
```
Entered the password when prompted as same as user bandit28. git repo cloned. then, Read the `README.md` file but there was nothing in that. therefore, 
checked the previous commit message, with the command : `git show` and we got the password which was removed 