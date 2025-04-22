## Objective : 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Solution : 
The password for next level is  "EeoULMCra2q0dSkYj561DX7s1CpBuOBt". 
first i connected to level 20 using ssh. Then, 

### step 1 : 
started the netcat listener sending the password of current level to it :
```
cat /etc/bandit_pass/bandit20 | nc -l -p 7777
```

- here `nc -l -p 7777` is starting netcat listener `-l`  on the port 7777
- `cat /etc/bandit_pass/bandit20` reads the password of current level and sends it to `nc` as input
### step 2 : 
Then, opened another terminal and connect to level 20 and this time run the binary file with with the 7777 as commandline argument:
```
./suconnect 7777
```
got the password for next level in first terminal.