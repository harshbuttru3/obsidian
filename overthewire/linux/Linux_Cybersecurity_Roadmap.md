
# 🗺️ Linux for Cybersecurity Roadmap

## ✅ Level 1: Linux Basics (Foundations)
- [x] Understand Linux directory structure (`/bin`, `/etc`, `/home`, etc.)
- [x] Learn basic commands: `ls`, `cd`, `pwd`, `mkdir`, `rm`, `cp`, `mv`
- [x] File viewing: `cat`, `less`, `more`, `head`, `tail`
- [ ] File types: `file`, symbolic/hard links, hidden files
- [x] Understanding absolute vs relative paths

## ✅ Level 2: Permissions & Ownership
- [x] Learn file permissions (`rwx`, numeric and symbolic)
- [x] Change permissions with `chmod`
- [x] Change ownership with `chown` and `chgrp`
- [ ] Learn SUID, SGID, and sticky bit
- [ ] Understand `umask`

## ✅ Level 3: Users, Groups, and Processes
- [ ] Create users and groups (`adduser`, `useradd`, `groupadd`)
- [ ] Use and edit `/etc/passwd`, `/etc/shadow`, `/etc/group`
- [ ] Switch users (`su`, `sudo`)
- [ ] Manage processes: `ps`, `top`, `kill`, `htop`
- [ ] Background & foreground processes (`&`, `jobs`, `fg`, `bg`)

## ✅ Level 4: Bash Scripting & Automation
- [ ] Learn bash script syntax (`#!/bin/bash`)
- [ ] Write scripts using `if`, `for`, `while`, `case`
- [ ] Use variables, functions, and command substitution
- [ ] Schedule tasks with `cron`
- [ ] Log script output to files

## ✅ Level 5: File Manipulation & Text Processing
- [ ] Use `grep`, `cut`, `awk`, `sed`, `xargs`, `sort`, `uniq`, `wc`
- [ ] Search files with `find` and `locate`
- [ ] Use pipes `|` and redirection `>`, `>>`, `<`, `2>`, `&>`

## ✅ Level 6: Networking Essentials
- [ ] Interface and IP commands: `ip a`, `ip r`, `ifconfig`
- [ ] Check ports: `netstat`, `ss`, `lsof`
- [ ] Test network: `ping`, `traceroute`, `nslookup`, `dig`
- [ ] Scan with `nmap`
- [ ] Create SSH keys, use `scp` and `rsync`

## ✅ Level 7: Services, Logs, and Monitoring
- [ ] Use `systemctl`, `journalctl` (for systemd services)
- [ ] Read log files in `/var/log/` (`auth.log`, `syslog`, `dmesg`)
- [ ] Monitor with `top`, `htop`, `iotop`
- [ ] Check boot info with `dmesg`

## ✅ Level 8: Security & Hardening
- [ ] Set up and use `ufw`, `iptables`, or `nftables`
- [ ] Disable unused services
- [ ] Configure fail2ban
- [ ] Learn SSH hardening
- [ ] Understand file integrity tools (like `aide`)

## ✅ Level 9: Exploitation & Privilege Escalation
- [ ] Exploit misconfigured `sudo` rights
- [ ] Exploit SUID binaries
- [ ] Abuse world-writable files & PATH vulnerabilities
- [ ] Enumerate system info using scripts like `LinPEAS` and `LinEnum`
- [ ] Crack `/etc/shadow` hashes with `john` or `hashcat`

## ✅ Level 10: Practice & Real-World Application
- [ ] Use **TryHackMe** or **Hack The Box** Linux rooms
- [ ] Complete **OverTheWire: Bandit**
- [ ] Simulate attacks on a VM using Metasploit/Kali
- [ ] Set up a vulnerable Linux VM (like VulnHub boxes)
- [ ] Document everything in **Obsidian** or a digital garden
