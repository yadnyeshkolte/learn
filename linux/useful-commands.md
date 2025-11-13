---
layout: default
title: Useful Commands
parent: Linux
nav_order: 1
---

# Useful Linux Commands


# Useful Linux Commands

| No.  | Linux Command                     | Description                                                 |
| ---- | --------------------------------- | ----------------------------------------------------------- |
| $1$  | `open .`                          | Open the folder you are in, in files GUI                    |
| $2$  | `open 'Git commands Linux.odt'`   | Will open this file in default operating software           |
| $3$  | `which javac`                     | Will show the path where the javac file is located          |
| $4$  | `ls -R`                           | Show the file in folders and subfolders                     |
| $5$  | `man echo`                        | Get the details of echo command.                            |
| $6$  | `rm -rf -R randomfolder`          | Delete all files and folders in randomfolder                |
| $7$  | `df -m`                           | Display free disk space                                     |
| $8$  | `du -g`                           | Display disk usage statistics                               |
| $9$  | `diff names.txt names2.txt`       | Compare the differences in txt files                        |
| $10$ | `locate javac`                    | Will locate anything related to javac                       |
| $11$ | `find . -type d`                  | Find directories in the current directory                   |
| $12$ | `find . -type f -name “*.txt”`    | Find all txt files in the current directory                 |
| $13$ | `find . -size +1k`                | Find files larger than 1KB in the current directory         |
| $14$ | `ls -l upper.txt`                 | Show the access permissions of the file                     |
| $15$ | `chmod u=rwx,g=rw,o=r upper.txt`  | Modify permissions for specific file                        |
| $16$ | `chmod 777 upper.txt`             | Give read, write, execute access to all                     |
| $17$ | `whoami`                          | Show the user of the computer                               |
| $18$ | `sudo chown root upper.txt`       | Change the owner of upper.txt to root user                  |
| $19$ | `sudo find . -perm 777`           | Find files with permissions 777 (read, write, execute)      |
| $20$ | `grep -w “string_name” algo.java` | Check if string_name exists in algo.java                    |
| $21$ | `grep -n “string_name” algo.java` | Print line numbers where string_name is present             |
| $22$ | `grep -winl “string_name” .`      | Check if any files contain string_name in current directory |
| $23$ | `history\| grep "ls"`             | Show history of the ls command`                             |
| $24$ | `alias`                           | Show the alias (short form of Linux commands)               |
| $25$ | `top`                             | Show running processes in terminal                          |
| $26$ | `$useradd ojaswi`                 | Add a new user                                              |
| $27$ | `passwd ojaswi`                   | Set password for new user                                   |
| $28$ | `userdel ojaswi`                  | Delete a user                                               |
| $29$ | `uname`                           | Show system information                                     |
| $30$ | `uname -o`                        | Show operating system name                                  |
| $31$ | `uname -m`                        | Show machine hardware name                                  |
| $32$ | `uname -r`                        | Show kernel version                                         |
| $33$ | `lscpu`                           | Show details of CPU                                         |
| $34$ | `nslookup google.com`             | Show network details of google.com                          |
