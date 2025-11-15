# Network Scanner (ARP Scanner)

A lightweight Python-based ARP Network Scanner built with Scapy.  
It discovers active hosts on a local network by sending ARP requests and parsing responses.

## Features
- Scans any subnet (example: 192.168.1.0/24)
- Automatically detects your MAC address
- Custom interface selection
- Clean table output
- Fast and silent ARP discovery

## Usage
sudo python scanner.py --target 192.168.1.0/24 

## Example Output
IP Address        MAC Address
---------------------------------------
192.168.1.1       00:11:22:33:44:55
192.168.1.14      f4:92:bf:2a:cd:68
