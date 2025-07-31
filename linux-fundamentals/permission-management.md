🔐 Permission Management
Linux permissions control who can access or modify files and directories, using a system based on users, groups, and others. This guide covers essential concepts, command usage, and practical examples with output.

🧾 Understanding Permissions
Every file and directory has:

An owner (user)

An associated group

Permission bits for user (u), group (g), and others (o)

Permissions:

r – Read

w – Write

x – Execute (or traverse in case of directories)

Example:


cry0l1t3@htb[/htb]$ ls -l

drw-rw-r-- 3 cry0l1t3 cry0l1t3 4096 Jan 12 12:30 scripts
🚫 Execute Permission on Directories
Execute permission (x) on a directory is required to enter or traverse it:


cry0l1t3@htb[/htb]$ ls -al mydirectory/

ls: cannot access 'mydirectory/script.sh': Permission denied
...
d????????? ? ? ? ? ? .
-????????? ? ? ? ? ? script.sh
Even if read permission exists, without x you can't access or traverse directory contents.

📊 Permission Breakdown
Example:


cry0l1t3@htb[/htb]$ ls -l /etc/passwd

-rwxrw-r-- 1 root root 1641 May 4 23:42 /etc/passwd
Breakdown:

Section	Meaning
-	Regular file
rwx	Owner: read, write, execute
rw-	Group: read, write
r--	Others: read
root root	User and group ownership
1641	File size in bytes
May 4	Last modification date

🛠 Changing Permissions
chmod – Change permission bits

cry0l1t3@htb[/htb]$ chmod a+r shell && ls -l shell

-rwxr-xr-x 1 cry0l1t3 htbteam 0 May 4 22:12 shell
Octal Notation

chmod 754 shell
Breakdown:

Entity	Binary	Octal	Permission
User	111	7	rwx
Group	101	5	r-x
Others	100	4	r--

👤 Changing Ownership
chown <user>:<group> <file>
Example:

cry0l1t3@htb[/htb]$ chown root:root shell && ls -l shell

-rwxr-xr-- 1 root root 0 May 4 22:12 shell
🧨 SUID & SGID
Set special permissions for programs to run with the owner's or group's privileges.

SUID (s in owner's execute bit)

SGID (s in group's execute bit)

⚠️ Be cautious: Misused SUID/SGID programs may allow privilege escalation. Refer to GTFObins for known abuses.

🔒 Sticky Bit
Sticky bit restricts file deletion in shared directories.

cry0l1t3@htb[/htb]$ ls -l

drw-rw-r-t 3 cry0l1t3 cry0l1t3 4096 Jan 12 12:30 scripts
drw-rw-r-T 3 cry0l1t3 cry0l1t3 4096 Jan 12 12:32 reports
t (lowercase): execute permission is present

T (uppercase): no execute permission

Only the file owner, directory owner, or root can delete files in such directories.

