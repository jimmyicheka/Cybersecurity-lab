# Hack The Box - Meow (Starting Point)

## 🖥 Machine Info
- **Name:** Meow  
- **Difficulty:** Very Easy (Starting Point)  
- **IP Address:** 10.x.x.x (changes when you spawn the machine)  
- **Date Completed:** 2025-08-24  

---

## 🔎 Reconnaissance Result
### Nmap Scan
```bash
nmap -sC -sV 10.x.x.x
-sC = default nmap script
-sV = For version scanning

Result:
23/tcp open  telnet  Linux telnetd

Findings:
Only port 23 (Telnet) is open.
Telnet service is running without requiring credentials.

🚪 Exploitation
Telnet is an old, insecure protocol that should not be used in modern environments. Since no authentication was configured, we can connect directly:

🏁 Flag
After connecting, I listed the files using ls and found flag.txt:

ls
cat flag.txt
✅ Copied the flag and submitted it on Hack The Box.

📚 Lessons Learned
Telnet is insecure because it transmits data in cleartext and can allow unauthenticated access.
Running reconnaissance with nmap -sC -sV quickly identified the open service and gave direction for exploitation.
Even simple misconfigurations (like no login) can lead to a full system compromise.
