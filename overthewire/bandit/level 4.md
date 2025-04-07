password is "4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw". 
when i entered in the "inhere" directory. there were 10 files named "-file00", "-file01", "-file02" ...... "-file09".  but there was only one file which was human readable. to find that file i ran the command `file ./*`. then i saw that only the file "-file07" has ASCII text. and others were "data". then i read the content of that file using the command `cat ./-file07`. and got the password.

### Notes: 
- `file` command returns the type of data that is found in the file. 