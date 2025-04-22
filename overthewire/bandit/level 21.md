## Objective : 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

## Solution : 
The password for next level is "tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q"

## Explanation :
First, i view the files of the directory `/etc/cron.d` as mentioned in the level goal. 
there was a file named cronjob_bandit22, read that file, The content of file was 
```bash
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22  
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null  
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null  
bandit21@bandit:/etc/cron.d$
```

This shows that, its running the cronjob_bandit22.sh script located in /usr/bin every second. so, after reading that script, 
```bash
bandit21@bandit:/tmp$ cat /usr/bin/cronjob_bandit22.sh    
#!/bin/bash  
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv  
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
we can see that this script is sending the password of bandit22 to a file in /tmp directory. 
Therefore, after running the `cat` command to read that file we got the password.