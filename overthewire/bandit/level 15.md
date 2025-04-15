## Objective : 
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

## Solution : 
The password for next level is "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx"
by using the command :
`openssl s_client -connect localhost:30001 -quiet < /etc/bandit_pass/bandit15` 

- The `openssl s_connect` command connected to port 30001 over SSL/TLS.
- `< /etc/bandit_pass/bandit15` piped the current password as **input** to the server.
- The `-quiet` flag hide all the SSL handshake debug info so i could clearly see the server's response.
- The server validated the password and returned the next level's password.

## Notes : 
### openssl : 
It is a powerful toolkit that implements the SSL and TLS protocols. It can be used to: 
- Create and manage SSL certificates.
- Encrypt/decrypt data
- Debug or connect to SSL -enabled services (like HTTPS, SMTPS, etc)
`s_client`  is a sub-command of `openssl` used to act like a client connecting to an SSL/TLS server. Think of it as `telnet` or `nc` (netcat), but for encrypted connections.