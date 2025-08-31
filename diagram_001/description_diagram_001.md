# Home ↔ ISP Topology (Packet Tracer)
## Overview
A simple home network, with wired and wireless interfaces set up to connect various devices. Home Router enables DHCP.  
Disclaimer: Integration with ISP, internet browsing and DNS server are out of scope. It is assumed that ISP assigns a statis private IPv4 address to its customers and NAT is enabled. 
## Diagram
![Screenshot of a CISCO Packet Tracer diagram](home_network_sim_2.jpg)
## Devices & Roles
- End Devices: 
  - PC0 (Home PC1)  
  - Server0 (Home Media Server)  
  - Printer0 (Home Network Printer)  
  - Laptop0 (Home Owner's Laptop)  
  - Tablet0 (Home Guest's Tablet)  
- HomeRouter-PT-AC (Home Wireless Router) 
---
## Networks
- **Home LAN1:** `192.168.10.0/24` or `255.255.255.0` (wired connection: PC0, Server0, Printer0)  
- **Home WLAN1:** `192.168.40.0/24` or `255.255.255.0` (Home Wi-Fi Network)  
- **Home WLAN2:** `192.168.50.0/24` or `255.255.255.0` (Guest Wi-Fi Network)  
- **Internet:** `x.x.x.x/xx` or `x.x.x.x` (Connection to ISP)  
---
## Addressing Table (Baseline)
| Device            | Interface          | IP Address       | Subnet Mask     | Default Gateway |
|-------------------|--------------------|------------------|-----------------|-----------------|
| PC0               | GigabitEthernet 1  | DHCP             |                 | 192.168.10.1    |
| Server0           | GigabitEthernet 2  | 192.168.20.100   |                 | 192.168.20.1    |
| Printer0          | GigabitEthernet 3  | 192.168.30.100   |                 | 192.168.30.1    |
| Wireless Router   | LAN (Port 1)       | 192.168.10.1     | 255.255.255.0   |                 |
| Wireless Router   | WLAN (SSID 1)      | 192.168.40.1     | 255.255.255.0   |                 |
| Wireless Router   | WLAN (SSID 2)      | 192.168.50.1     | 255.255.255.0   |                 |
| Laptop            | Wireless 1         | DHCP             |                 |                 |
| Tablet            | Wireless 2         | DHCP             |                 |                 |

---
## DHCP Server (Home Router)
- **LAN1 Pool:** `192.168.10.100 – 192.168.10.199` (GW: `192.168.10.1`)  
- **WLAN1 Pool:** `192.168.30.100 – 192.168.30.199` (GW: `192.168.30.1`)  
- **WLAN2 Pool:** `192.168.40.100 – 192.168.40.199` (GW: `192.168.40.1`)  
