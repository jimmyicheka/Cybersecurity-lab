# 🧠 HTB: Basic Lab Walkthrough

This is a walkthrough of a basic Hack The Box lab I completed.

## 🖥️ Machine Info
- Name: `Basics`
- Difficulty: Easy
- Category: Linux Fundamentals

## 🔍 Recon
- `nmap -sV -sC -oN basics-nmap.txt <target-ip>`
  - Found SSH (22) and HTTP (80)

## 📂 Web Exploration
- Visited the web page, found a hidden directory `/admin/`
- Discovered login page and used `admin:admin` to gain access

## 🔐 Gaining Access
- Used `netcat` to send reverse shell
- Got shell as user

## 🎯 Privilege Escalation
- Found SUID binary `/usr/bin/special`
- Ran it to get root access

## 📝 Takeaways
- Enumeration is key
- Try default creds
- SUID = potential root

---
More labs coming soon...
