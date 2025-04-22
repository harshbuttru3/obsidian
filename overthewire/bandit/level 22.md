## Objective : 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Solution : 
The password for next level is "0Zf11ioIjMVN551jX3CmStKLYqjk54Ga"

## Explanation :
When viewed the content of /etc/cron.d, got a file named `cronjob_bandit23`
read that file using `cat cronjob_bandit23` it is running `cronjob_bandit23.sh` script which is located in /usr/bin. 
The content of that script was : 
```bash
#!/bin/bash  
  
myname=$(whoami)  
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)  
  
echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"  
  
cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
here , in this bash script, we can clearly see that 
- it's creating a variable "myname" and storing the current user's name in it with `whoami` command. then,
- it is creating another variable named "mytarget" and storing the hashed version of the phrase `I am user $myname` , where `$myname` stores "bandit23" because this script is being run by bandit23 user.
- and then, this script is storing the password of bandit23 in the file /tmp/$mytarget

So, we can do similar thing to get the $mytarget variable data. thus we can run the commands : 
```bash
mytarget=$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
echo $mytarget
cat /tmp/$mytarget ## or cat /tmp/<the contents of $mytarget>
```
voila, we got the password!