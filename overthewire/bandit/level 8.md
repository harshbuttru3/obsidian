## objective : 
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Solution : 
The password is "4CKMh1JI91bUIZZPXDqGanal4xvAg0JM" . 
The required command is `sort data.txt | uniq -u` 

## Explanation : 
1. `sort data.txt` : 
	- Alphabetically sorts the lines in the file(needed because `uniq` only works on consecutive duplicates)
2. `uniq -u` : 
	-  Shows only unique lines (lines that appear once). 
3. Combine them with a pipe `|` so that the output of `sort` is passed to `uniq` 