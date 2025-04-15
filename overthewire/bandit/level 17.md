## Objective : 
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
## Solution : 
The password for bandit 18 is "x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO" 

## Explanation : 
since there are two file **passwords.old** and **passwords.new** and the password is in **passwords.new** and is the only line that has been changed between these two file, thus we can use the `diff` command to differentiate between two files line by line so by running the command : 
`diff passwords.new passwords.old` i got the new password. 