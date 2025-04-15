## Objective : 
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Solution : 
The password for next level is "cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8" .

since the session got closed as soon i tries to ssh into bandit18 with a message "Bye Bye ! ". and in objective we can clearly see that the password for "bandit19" is stored in the readme file located at the home directory of bandit18. we can run a bash command while connecting with ssh itself using the command : 
`ssh -p 2220 bandit18@bandit.labs.overthewire.org "cat ~/readme"` 