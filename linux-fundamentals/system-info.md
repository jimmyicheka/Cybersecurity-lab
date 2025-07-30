# 🧠 Linux System Information & Enumeration

Useful commands for gathering system, user, and network details during enumeration or admin tasks.

## 🔍 System & Kernel Info

| Command       | Purpose                                         |
|---------------|-------------------------------------------------|
| `uname -a`    | Full kernel, architecture, and OS info          |
| `hostname`    | Displays the system’s hostname                  |
| `uptime`      | Shows system uptime                             |
| `pwd`         | Displays present working directory              |

## 👤 User Identity & Groups

| Command     | Purpose                                            |
|-------------|----------------------------------------------------|
| `whoami`    | Shows current username                             |
| `id`        | Lists UID, GID, and group memberships              |
| `groups`    | Shows all groups the user belongs to              |

## 👥 Active Users & Sessions

| Command   | Purpose                                   |
|-----------|-------------------------------------------|
| `who`     | Lists users currently logged in           |
| `w`       | Shows who is logged in and what they’re doing |
| `last`    | Displays login history                    |

## 🌐 Network & Interfaces

| Command     | Purpose                                 |
|-------------|------------------------------------------|
| `ifconfig`  | Shows network interfaces (deprecated)    |
| `ip a`      | Modern alternative to `ifconfig`         |
| `netstat -tuln` | Lists open ports and listening services |
| `ss -tuln`  | Faster alternative to netstat            |

## 💾 Hardware & Devices

| Command     | Purpose                          |
|-------------|----------------------------------|
| `lsblk`     | Lists disk devices & partitions  |
| `lsusb`     | Lists USB devices                |
| `lspci`     | Lists PCI devices                |
| `lsof`      | Lists open files and the processes using them |

📂 File Identification & Timestamps
Use these commands to inspect files, their types, and modification times — crucial during enumeration or digital forensics.

Command	Purpose
file filename	Determines the file type (ASCII, binary, etc.)
stat filename	Displays file metadata (size, UID, GID, timestamps)
ls -lt	Lists files by most recent modification time
find /path -type f -newer file	Finds files newer than a given file
`find /var/backups -printf '%TY-%Tm-%Td %TT %p\n'	sort`

✅ Example:
To identify the last modified file in /var/backups, you could use:

bash
Copy
Edit
ls -lt /var/backups | head -n 1

# 🔄 File Descriptors & Redirections

This section breaks down how Linux handles input/output streams using file descriptors and redirection. Based on learning from the HTB Academy Linux Fundamentals module.

---

## 📌 What are File Descriptors?

File Descriptors (FDs) are numeric identifiers used by the kernel to manage open files and I/O resources.

| Stream       | Descriptor | Description                 |
|--------------|------------|-----------------------------|
| `STDIN`      | 0          | Input stream (e.g., keyboard) |
| `STDOUT`     | 1          | Standard output (e.g., terminal) |
| `STDERR`     | 2          | Error output (e.g., error messages) |

---

## 🧪 Basic Usage

### ✅ STDIN to STDOUT (echo via `cat`)
```bash
cat
Think Outside The Box

---

More coming soon as I go deeper into Linux exploration 🚀
