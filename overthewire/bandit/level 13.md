## Objective : 
The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on.

## Solution : 
The password for bandit14 is "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS"

## Explanation : 
When i logged in into bandit13, i got the private ssh key for bandit14 "sshkey.private". copied that private ssh key into my local machine using the `scp` command utility as follow: 
`scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private .` 
gave the password for bandit 13 when prompted. 

The "sshkey.private"  file was succesfully copied into my local machine, 
Gave the permission to sshkey.private file for read and write only to current user with the command: 
	`chmod 600 sshkey.private`
Then, logined to bandit14 using the ssh with the command
`ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`

Then i was successfully logined into bandit14. 
The password file was inside the /etc/bandit_pass/bandit14 as described in objective. just read that file using `cat` 