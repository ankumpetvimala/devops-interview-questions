# devops-interview-questions

Linux Interview Questions

1. What is the difference between a process and a thread in Linux?

A process is an independent program with its own memory space.

A thread is a lightweight sub-process that shares memory and resources with other threads in the same process.

2. What is the difference between a hard link and a soft link in Linux?

Hard link: Points to the same inode as the original file. Cannot span file systems.

Soft link (symbolic link): Points to the filename and can span across file systems.

3. How can you check the memory usage of a Linux system?

free -h
top
vmstat
htop

4. How do you find the IP address of a Linux system?

ip addr
ifconfig (deprecated)
hostname -I

5. What is the purpose of the "chmod" command in Linux?

It is used to change the permissions of files and directories.

6. What is the purpose of the "grep" command?

grep is used to search for patterns or strings in files or output.

7. How do you change the password for a user in Linux?

passwd <username>

8. What is the purpose of the "cron" daemon in Linux?

It schedules and runs repetitive tasks at specified times.

9. How do you schedule a cron job in Linux?

crontab -e

Format: * * * * * command

10. Disk space full issue?

Use df -h to check space.

Use du -sh * to find large files.

Clear logs, old files, or expand disk.

11. Running out of memory?

Use free -m, top, or htop.

Kill memory-hogging processes.

Add swap memory if needed.

12. How do you troubleshoot high CPU usage on a Linux server?

Use top, htop, ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu

13. Describe the boot process of a Linux system?

BIOS/UEFI → Bootloader (GRUB) → Kernel → init/systemd → Runlevel → Login

14. Transfer a large file securely between two Linux servers:

Use scp, rsync, or sftp

scp largefile user@remote:/path/

15. Restore deleted file from backup:

Identify backup tool (rsync, snapshots, etc.)

Locate backup path and use cp or rsync to restore

16. SSH connection issue troubleshooting:

Check network connectivity

Verify SSH service is running

Check firewall and security group settings

17. Find files larger than 100MB in /home:

find /home -type f -size +100M

18. What is inode?

Data structure storing metadata of files in Linux.

19. Booting process in Linux:

Covered in Q13

20. Clear server space when full:

Clear log files

Remove unused files

Use journalctl --vacuum-time=7d

21. Types of OS patching:

Security updates, kernel updates, application patching using yum/apt.

22. Daily Linux commands:

cd, ls, cat, grep, top, df, du, systemctl, journalctl, scp

23. Linux file permission types:

Read (r), Write (w), Execute (x) for User, Group, Others

Shell Script Interview Questions

1. What is CRONTAB?

Tool to schedule jobs on Linux using cron daemon.

2. Disk usage with shell script:

df -h
du -sh *

3. Purpose of the shebang line:

Specifies interpreter to run the script. Example: #!/bin/bash

4. Use of $# in shell scripting:

Represents number of positional arguments passed to a script.

5. Script to check vowels in a string:

read -p "Enter string: " str
echo "$str" | grep -i -o [aeiou] | wc -l

6. @, *, n, ? in shell scripting:

@ and * used in loops for arguments

? represents a single character wildcard

7. Detect if server is virtualized:

dmidecode | grep -i product
lscpu | grep Hypervisor

8. Special variables:

$0, $1, $#, $*, $@, $$, $?, $!
