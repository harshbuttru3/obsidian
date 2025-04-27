
## Objective : 
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

## Solution : 
The password for next level is "s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ"

[Medium Writeup](https://medium.com/@coturnix97/overthewires-bandit-25-26-shell-355d78fd2f4d)
For this level, i looked for this medium writeup. 

## Explanation : 
in level 25, we got the ssh key for level 26, copied it in local machine and tried to access level 26 but got kicked out of it as soon i ssh into it.

### Step 1. 
As the level goal has mentioned that, bandit 26 is not `/bin/bash`, but something else. Therefore, checked the shell of bandit26 via the command : `cat /etc/passwd | grep bandit26`  and find out that, it has an custom shell which executes `more`.

### Step 2. 
Therefore, resized the shell to minimum size possible and tried to ssh again into bandit26 and we were in. 

### Step 3. 
Then, pressed `v` to open `vim` then, opened the password for bandit26 via opening another file with vim via the pressing `:e /etc/bandit_pass/bandit26`. we now have password for bandit26 but still we can't access the shell 

### Step 4.
now, pressed `:set shell=/bin/bash` in vim and it set the shell to bash. then entered the command `:shell` and then we've got the shell. 