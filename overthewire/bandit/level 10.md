## Objective : 
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Solution : 
The password is "dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr"
we can decode the base64 data with the command 
`base64 -d data.txt` or `cat data.txt | base64 -d`, here `-d` stands for "decode". 