# Redco Developments - Network Design and Implementation

A multi-branch enterprise network designed and simulated in **Cisco Packet Tracer** for Redco Developments, covering two office locations - the **Kandy Head Office** and the **Galle Southern Branch**. This project was completed as part of an HND Networking assignment covering network design, VLAN configuration, IP subnetting, routing protocols, server setup, and network testing.

***

## Project Overview

The network is designed with a hierarchical topology - **star topology** at the access layer for departmental workstations and **partial mesh** in server rooms for fault tolerance. Both branches are interconnected via a WAN link using **RIP (Routing Information Protocol)** for dynamic inter-branch routing and **IPSec VPN** for secure inter-site data transfer.

***

## Network Design Highlights

- Hierarchical three-layer design (Access, Distribution, Core)
- VLAN segmentation per department to reduce broadcast domains and improve security
- Inter-VLAN routing via Layer 3 switches
- Dynamic IP allocation using DHCP servers on both branches
- Internal DNS and Web servers on both branches
- WPA2-secured wireless access for customer service areas, boardrooms, and sales
- IoT device isolation (IP cameras, automated gates, lighting) on dedicated VLANs at Galle branch
- SSH and Telnet remote management configured on routers and switches
- RIP-based dynamic routing between Kandy and Galle routers

***

## IP Addressing Scheme

| Branch   | Network Range      | Purpose                  |
|----------|--------------------|--------------------------|
| Kandy    | 200.100.10.0/24    | Kandy branch departments |
| Galle    | 200.100.20.0/24    | Galle branch departments |
| Servers  | 200.100.50.0/24    | Centralized server room  |
| WAN Link | 200.100.30.0/24    | Inter-branch WAN link    |

***

## VLANs Configured

**Kandy Branch:**
- Reception
- Sales
- Customer Service
- Developers
- Boardroom
- HR
- Admin
- Directors
- Accounting
- IT Department
- Server Room

**Galle Branch:**
- Reception
- Customer Service
- Developers
- Administration
- HR
- Accounting
- IT Department
- Server Room
- IoT Devices

***

## Servers Configured

Both branches include the following servers:
- **DHCP Server** - automatic IP allocation for all workstation VLANs
- **DNS Server** - internal name resolution
- **Web Server** - internal intranet access

***

## Protocols Used

| Protocol    | Purpose                                              |
|-------------|------------------------------------------------------|
| TCP/IP      | Core communication protocol suite                   |
| DHCP        | Automatic IP address assignment across VLANs        |
| DNS         | Internal hostname to IP resolution                  |
| RIP         | Dynamic routing between Kandy and Galle branches    |
| IPSec VPN   | Secure encrypted inter-branch communication         |
| SSH         | Secure remote management of switches and routers    |
| Telnet      | Backup remote access for router management          |
| WPA2        | Wireless security for access points                 |

***

## Testing Performed

All tests were carried out in Cisco Packet Tracer simulation mode and verified via CLI screenshots.

- Intra-VLAN ping tests (same department connectivity)
- Inter-VLAN ping tests (cross-department routing via Layer 3 switch)
- DHCP IP assignment verification (Sales, HR, and other workstation VLANs)
- SSH access from Admin PC to Kandy and Galle switches
- Telnet access from Admin PC to Kandy and Galle routers
- Inter-branch ping: Galle PC to Kandy VLAN 40 gateway (`200.100.10.65`)
- Inter-branch ping: Kandy PC to Galle VLAN 30 gateway (`200.100.20.1`)
- Traceroute: Galle PC to Kandy WAN interface (`200.100.30.6`)
- Traceroute: Kandy PC to Galle WAN interface (`200.100.30.2`)

All 14 test cases passed successfully.

***

## Repository Contents

```
redco-network-design/
├── redco_network.pkt         # Cisco Packet Tracer simulation file
└── README.md
```

***

## How to Open the Packet Tracer File

1. Download and install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (requires a free Cisco NetAcad account)
2. Open `redco_network.pkt` in Packet Tracer
3. Use **Simulation Mode** to trace packets between devices
4. Use the CLI on routers and switches to inspect VLAN, routing, and DHCP configurations

***

## Author

**Kaveesha Amiru** | Student ID: 00272845  
HND in Computing - Networking Module  

> This project was developed for academic purposes.
