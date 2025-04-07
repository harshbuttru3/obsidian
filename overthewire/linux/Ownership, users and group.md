# Users: 
+ Each person (or service) that can log in to a linux system is a user. 
- Examples: `root` , `harsh`,  `www-data`,  `bandit6`
# Groups: 
+ Groups are collections of users. 
+ permissions can be assigned to a group so all users in that group share access. 
+ Examples: `sudo`, `staff`, `bandit6`, etc.

# Permissions: 
What the owner, group, and others can do with the file.

### To view ownership and permission
use `ls -l` , the output will be something like this: 
`-rw-r--r-- 1 bandit7 bandit6  33 Apr  7 12:00 secret.txt` 

+ `-rw-r--r--` : File permissions
+ `1` : Number of links
+ `bandit7` : Owner (user)
+ `bandit6` : Group
+ `33` file size in bytes
+ `Apr 7 12:00` Last modified date
+ `secret.txt` : File name

## File permission format
`-rw-r--r--` this is the list of permission given to a specific file/folder.

`-` : File type (`-` = file, `d` = directory)
`rw-` : Owner (bandit7) > Read + Write
`r--` : Group (bandit6) > Read only
`r--` : Others (everyone else) > Read only.

Each group has 3 positions: 
1. `r` for Read and has value **4** 
2. `w` for Write and has value **2** 
3. `x`  for execute and has value **1** 
Just add the values to set permissions: 



| Code | Meaning                        |
| ---- | ------------------------------ |
| 0    | No permissions                 |
| 4    | Read only                      |
| 5    | `4+1` > Read, Execute          |
| 6    | `4+2` > Read, Write            |
| 7    | `4+2+1` > Read, Write, Execute |

## Change Onwership (requires root)

To change the ownership of files we can run the command: 
`chown user:group filename` for example if we run `chown bandit7:bandit6 secret.txt` this command would changes Owner to bandit7 and group to bandit6.

#### change Group only 
 `chgrp bandit6 filename`

## Understanding `chmod` ( Change Mode )
Each file has 3 sets of permissions: 

| Group      | Applies to    |
| ---------- | ------------- |
| User (u)   | Owner         |
| Group (g)  | Group         |
| Others (0) | Everyone else |
#### Example 
1.  `chmod 755 script.sh`  
This command will change the mode of file(i.e permissions of file for user, group and others)

| Who    | value | Meaning    |
| ------ | ----- | ---------- |
| User   | 7     | rwx(4+2+1) |
| Group  | 5     | r-x(4+0+1) |
| Others | 5     | r-x(4+0+1) |



2. `chmod 644 myfile.txt`


| Who    | value | Meaning     |
| ------ | ----- | ----------- |
| User   | 6     | rw- (4+2+0) |
| Group  | 4     | r-- (4+0+0) |
| Others | 4     | r-- (4+0+0) |

## Symbolic Mode 
We can use letters also to add or remove or set permissions

| Commands             | Meaning                 |
| -------------------- | ----------------------- |
| `chmod u+x file.sh`  | Add execute to user     |
| `chmod g-w file.txt` | Remove write from group |
| `chmod 0=r file.txt` | set others to read-only |
