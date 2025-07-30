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

---

More coming soon as I go deeper into Linux exploration 🚀
