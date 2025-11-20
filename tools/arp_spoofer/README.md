# ARP Spoofer

A simple Python tool that performs **ARP spoofing / ARP poisoning** using Scapy.  
This script sends forged ARP replies to redirect traffic between a target and the network gateway, creating a basic Man-in-the-Middle setup for educational security testing.

> ⚠️ **For educational and authorized use only.**  
> Do not use this on networks you do not own or have explicit permission to test.

---

## Features

- Automatically retrieves MAC addresses using ARP requests  
- Spoofs ARP tables for both the target and gateway  
- Uses `sendp()` for reliable Layer-2 packet delivery  
- Sends continuous ARP poisoning packets  
- Restores to original state when finished



