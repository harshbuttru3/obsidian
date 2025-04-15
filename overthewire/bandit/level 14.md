## Objective : 
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Solution : 
The password for next level is "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo"

Got this password by submitting the current password "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" to localhost at port 30000 using the command :
`cat /etc/bandit_pass/bandit14 | nc localhost 30000` 

- `cat` reads the current level's password
- `nc` sends it to the specified port
- The server replies with the password for the next level.