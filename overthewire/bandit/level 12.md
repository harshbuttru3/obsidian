## Objective : 
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Solution : 
The password is "FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn"

## Explanation : 

###  1. Create a temporary working directory : 
First of all i created a random directory safely under `/tmp` with the commands : 
```bash
cd /tmp
WORKDIR=$(mktemp -d)
cd $WORKDIR
```


###  2. Copy and prepare the file :
```bash
cp /home/bindit12/data.txt
xxd -r data.txt > data.bin
```
This reverses the hexdump into binary and save it into `data.bin` .

here, `xxd -r` reverses hexdump.

#### hexdump : 
A hexdump is a representation of binary data in a human-readable format, where the data is shown as hexadecimal values (base 15) along with their corresponding ASCII characters (if printable). It helps you visualize and analyze the raw binary contents of a file. 

To Generate a Hexdump, you can use tools like `xxd` (on linux/macOS) or `hexdump` to generate a hexdump. For example : 
`xxd filename` or `hexdump -C filename`.  Both will display the hexadecimal representation of the file's contents. 

### 3. Begin the Decompression Loop :
Keep checking the file type and decompressing: 
`file data.bin`
This will say something like: 
-  gzip compressed data
- bzip2 compressed data
- POSIX tar archive 
- ASCII text

Depending on what `file` tells, do: 

### a)   If it's gzip : 
```bash
mv data.bin temp.gz
gunzip temp.gz
mv temp data.bin
```
#### Explanation : 
Here, 
1. `mv data.bin temp.gz`  renames "data.bin"  to "temp.gz".
2. `gunzip temp.gz` unzip the "temp.gz" archive to  "temp"
3. `mv temp data.bin` again renames the "temp" to data.bin

+ Again, we will check the file type of data.bin with `file data.bin`  command. 
### b)   If it's bzip2 : 

```bash
mv data.bin temp.bz2
bunzip2 temp.bz2
mv temp data.bin
```

### c)  If it's a tar archive(POSIX) : 
```bash
mv data.bin temp.tar
tar -xf temp.tar
```

and finally, we will get : 
### d) ASCII text : 
we can open the file with `cat`, `less`, or `strings`  to find the password.  

## Bonus : 
asked chatgpt to automate this process with a bash script. here's the code: 
```bash
#!/bin/bash

# Make a temporary working directory
WORKDIR=$(mktemp -d)
cd "$WORKDIR" || exit

# Copy the data.txt file
cp /home/bandit12/data.txt .

# Decode hex dump to binary
xxd -r data.txt > data.bin

# Loop until we reach a plain text file
while true; do
    FILETYPE=$(file data.bin)

    echo "[*] Current type: $FILETYPE"

    case "$FILETYPE" in
        *gzip*)
            mv data.bin temp.gz
            gunzip temp.gz
            mv temp data.bin
            ;;
        *bzip2*)
            mv data.bin temp.bz2
            bunzip2 temp.bz2
            mv temp data.bin
            ;;
        *tar\ archive*)
            mv data.bin temp.tar
            tar -xf temp.tar
            # Assume there's only one file inside each tar
            NEWFILE=$(ls | grep -v data.txt | grep -v temp.tar)
            mv "$NEWFILE" data.bin
            ;;
        *ASCII\ text*)
            echo "[+] Final result:"
            cat data.bin
            break
            ;;
        *)
            echo "[!] Unknown file type. Exiting."
            break
            ;;
    esac
done

```
