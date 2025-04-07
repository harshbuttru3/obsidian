password is "morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj" 
The objective of this exercise is to find the file containing password and the file has following properties. 
1. Owned by user: bandit7
2. Owned by group: bandit6
3. Exactly 33 bytes in size

for this i ran the command: 
`find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null`

`find /` start the search at the root directory 
`-type f` look only for files (not directories or devices)
`-user bandit7 -group bandit6` look for the file owned by user and group respectively.
`-size 33c` file size is 33 bytes. (c = characters/bytes)
`2>/dev/null` Hide permission errors.

	2 = stderr(error messages)
	`>/dev/null` = send them to the void(hide them)
