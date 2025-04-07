## Objective : 
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Solution : 
The password is "FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey". 
we can run the command `strings data.txt | grep '===' ` 


## Explanation : 


| Tool      | Purpose                                        |
| --------- | ---------------------------------------------- |
| `strings` | Extracts human-readable text from binary files |
| `grep`    | Filters lines based on a pattern               |
| `cat`     | Displays file content                          |
first we got all the human readable text from the binary file "data.txt" file with the `strings` command and piped the output with `grep` command to find only the letter preceded by several "==="