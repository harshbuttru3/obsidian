password is "HWasnPhtq9AVKe0dmk45nxy20cvUa6EG".
The objective of the challege is to find the file containing password for next exercise, the file has following properties: 
1. human redable i.e plain text, "ASCII text" or utf-8 encoding
2. not executable
3. 1033 bytes in size.
therefore to find this file. i ran the command,
`find inhere -type f -size 1033c ! -executable -exec file {} \; | grep "ASCII text"`

*Find* command is used to search files in directories recursively.
`find [path] [conditions] [actions]`

`-type f`: only return regular files(not directories, syslinks, etc).
`-size 1033c`: exact size we want. **c** is size in bytes so this filters files that are exactly 1033 bytes.
`! -executable` : for non executables files
`-exec file {} \;` : 
1. `file` tells you what kind of data is in the file.
2. `{}` is a placeholder for the filename.
3. `\;` ends the `-exec` command.

`grep "ASCII text` : we only want human-readable text, so we look for output lines where `file` says "ASCII text".