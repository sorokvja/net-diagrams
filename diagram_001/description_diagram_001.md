# Home ↔ ISP Topology (Packet Tracer)
## Overview
A home LAN (wired + Wi-Fi) connects to an ISP router, which uplinks to an “Internet” server.  
The Home Router provides DHCP, NAT, and wireless access.

## Diagram
![Screenshot of CISCO Packet Tracer diagram](https://)

## Devices & Roles
- **End Devices**  
  - PC0 (home PC, wired connection to the home router)  
  - PC1 (home PC, wired connection to the home router)  
  - PC2 (management PC connected to the ISP router via console cable)  
  - Printer0 (network printer)  
  - Laptop0 (wireless, home network)  
  - Laptop1 (wireless, guest network)  

- **Home Router (Wireless Router-PT AC)**  
  - LAN gateway, DHCP server, NAT, Wi-Fi AP  

- **ISP Router (Router-PT, Router0)**  
  - Provider edge between home and server  

- **Server (Server-PT, Server0)**  
  - Simulated Internet host  

## Networks
- **Home LAN1:** `192.168.10.0/24` (PCs)  
- **Home LAN2:** `192.168.20.0/24` (Printer)  
- **Home WLAN1:** `192.168.30.0/24` (Home Wi-Fi)  
- **Home WLAN2:** `192.168.40.0/24` (Guest Wi-Fi)  
- **Home ↔ ISP (WAN P2P):** `10.0.0.0/30`  
- **ISP ↔ Server (P2P):** `203.0.113.0/30` *(TEST-NET-3, safe for documentation)*  

## Interface / IP Assignments

| Interface / Node           | Purpose / Configuration | IP / Mask            |
|----------------------------|-------------------------|----------------------|
| **Home Router – LAN1**     | Connect Wired PCs       | `192.168.10.1 /24`   |
| **Home Router – LAN2**     | Printer                 | `192.168.20.1 /24`   |
| **Home Router – WLAN1**    | Home Wi-Fi              | `192.168.30.1 /24`   |
| **Home Router – WLAN2**    | Guest Wi-Fi             | `192.168.40.1 /24`   |
| **Home Router – WAN**      | To ISP Router           | `10.0.0.2 /30`       |
| **ISP Router – to Home**   | P2P to Home Router      | `10.0.0.1 /30`       |
| **ISP Router – to Server** | P2P to Server           | `203.0.113.1 /30`    |
| **Server0**                | Internet host           | `203.0.113.2 /30`    |
| **PC0, PC1**               | DHCP                    | `192.168.10.x /24`   |
| **Printer0**               | Static                  | `192.168.20.x /24`   |
| **Laptop0**                | DHCP                    | `192.168.30.x /24`   |
| **Laptop1**                | DHCP                    | `192.168.40.x /24`   |

## DHCP (Home Router)
- **LAN1 Pool:** `192.168.10.100 – 192.168.10.199` (GW: `192.168.10.1`)  
- **LAN2 Pool:** `192.168.20.100 – 192.168.20.199` (GW: `192.168.20.1`)  
- **WLAN1 Pool:** `192.168.30.100 – 192.168.30.199` (GW: `192.168.30.1`)  
- **WLAN2 Pool:** `192.168.40.100 – 192.168.40.199` (GW: `192.168.40.1`)  
- **DNS:** `8.8.8.8` (or ISP DNS)  

## Routing
### Home Router
to be added at some point

## CISCO Router Configuration
to be added at some point
