## Objective : 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Solution : 
The password for next level is "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO"

## Explanation : 
As instructed, when i viewed the permissions of the files located in home directory by the command `ls -la`.
got a binary file with permission 's'. which means we can run this binary as another user, 
```
-rwsr-x---  1 bandit20 bandit19 14884 Apr 10 14:23 bandit20-do
```

when i run this binary without any any argument as instructed in objective, with the command `./bandit20-do` got the help menu (how to use it). 
```
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id

```
then, i read the password of bandit20 which is located in /etc/bandit_pass/bandit20. 
which doesn't have read persmission as bandit19 but as bandit20. so by running the command ` ./bandit20-do cat /etc/bandit_pass/bandit20` we got the password for bandit20 which i mentioned earlier.
