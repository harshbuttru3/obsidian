
## Objective : 
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Solution : 
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN 

## Explanation : 
`ssh`  into bandit27 via the password got in previous level. 

then, 
```bash
cd /tmp
mkdir bandit27repo && cd bandit27repo
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
```
Entered the password for bandit27-git as same as user  bandit27. 

here, `GIT_SSH_COMMAND='ssh -p 2220` uses ssh port 2220, the default port for ssh is 22. 

cloned the git repository names `repo`, in that repository, there was a `README` file. And this file contains Password for next level. 