# Hack The Box - Fawn (Starting Point)

## 🖥 Machine Info
- **Name:** Fawn  
- **Difficulty:** Very Easy (Starting Point)  
- **IP Address:** 10.x.x.x (changes when you spawn the machine)  
- **Date Completed:** 2025-08-24  

---

## 🔎 Reconnaissance
### Nmap Scan
nmap -sC -sV 10.x.x.x


Results:
21/tcp open  ftp
| ftp-anon: Anonymous FTP login allowed (FTP code 230)

Findings:
Port 21 (FTP) is open.
Anonymous login is enabled, meaning we can connect without credentials.

🚪 Exploitation
Connected to the FTP service using anonymous login:
ftp 10.x.x.x
When prompted:
Username: anonymous
Password: (pressed Enter)

Now listed the files:
ls
Found flag.txt. 

Download it:
get flag.txt

🏁 Flag
Read the file locally:
cat flag.txt


📚 Lessons Learned
FTP servers may be misconfigured to allow anonymous access.
Using nmap -sC -sV helps detect anonymous login automatically.
Always check available files after logging in — sensitive information is often left exposed.
