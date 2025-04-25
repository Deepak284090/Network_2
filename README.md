# Network-2 - 5-Floor Office Network Configuration

## 📘 Project Description

- The project was to simulate a professional network deployment for a 5-floor office building.
- The goal was to design and implement an efficient, scalable network architecture using Cisco Packet Tracer.
- The network design had to include proper IP allocation using VLSM, server placements, and a routing strategy ensuring reliable inter-floor communication.
- Each floor was assigned specific roles, such as hosting email, FTP, HTTP, DNS, and DHCP servers.
- Due to simulation constraints, a limited number of devices were used per floor to represent the full setup.
- Dynamic routing using RIP was implemented to automate route management between floors.

---

## 🏢 Floor-wise Device and IP Plan

| Floor | PCs | Subnet Mask       | Network Range             | Hosts Needed | Hosts Available | Gateway      |
|-------|-----|--------------------|----------------------------|----------------|------------------|--------------|
| 1     | 5893 | 255.255.224.0      | 10.0.64.0 - 10.0.95.255    | 5893           | 8190             | 10.0.64.1    |
| 2     | 12345| 255.255.192.0      | 10.0.0.0 - 10.0.63.255     | 12345          | 16382            | 10.0.0.1     |
| 3     | 128  | 255.255.255.0      | 10.0.17.0 - 10.0.17.255    | 128            | 254              | 10.0.17.1    |
| 4     | 234  | 255.255.255.0      | 10.0.16.0 - 10.0.16.255    | 234            | 254              | 10.0.16.1    |
| 5     | 2456 | 255.255.240.0      | 1.0.0.0 - 1.0.15.255       | 2456           | 4094             | 1.0.0.1      |

*Note: Due to Cisco Packet Tracer limitations, only 7 PCs were placed per floor for simulation purposes.*

---

## 🔧 Server Deployment Plan

| Service     | Floor Location | Server Device         |
|-------------|----------------|------------------------|
| Email       | 1st Floor      | Email Server           |
| FTP         | 2nd Floor      | FTP Server             |
| HTTP        | 3rd Floor      | HTTP Server            |
| DNS & DHCP  | 5th Floor      | DNS & DHCP Server      |

---

## 🌐 Topology Design

- **Star Topology**: Implemented on Floors 1 to 4 to simplify troubleshooting and improve performance.
- **Mesh Topology**: Implemented on Floor 5 for high availability and fault tolerance.
- **Router Ring Topology**: All 5 routers are connected in a ring for resilient inter-floor communication.

---

## 📡 Addressing Scheme

- **Class A Private IPs**: Used on Floors 1 and 2.
- **Class A Public IPs**: Used on Floors 3, 4, and 5.
- **VLSM (Variable Length Subnet Masking)**: Applied to ensure efficient IP allocation across subnets.

---

## 🔁 Routing Strategy

- **Dynamic Routing Protocol**: RIP (Routing Information Protocol) is configured across all routers to handle inter-floor communication dynamically.
- **Router Connections (Using /30 subnet mask)**:
  - 1st ↔ 2nd: `2.0.0.0`
  - 2nd ↔ 3rd: `2.0.0.4`
  - 3rd ↔ 4th: `2.0.0.8`
  - 4th ↔ 5th: `2.0.0.12`
  - 1st ↔ 5th: `2.0.0.16`

---

## 🔌 Network Devices

- **Switches**: One per floor (Star topology)
- **Routers**: 5 total, one per floor
- **Access Devices**: PCs and Laptops (7 per floor for testing)
- **Servers**: Placed as per service requirements

---

## 📍 Gateways

Each floor uses a unique default gateway:

- Floor 1: `10.0.64.1`
- Floor 2: `10.0.0.1`
- Floor 3: `10.0.17.1`
- Floor 4: `10.0.16.1`
- Floor 5: `1.0.0.1`

---

## 📊 Subnet Summary

Every subnet was calculated using VLSM to maximize address efficiency. Each includes:
- Subnet Address
- Valid Host IP Range
- Broadcast Address

---

## ✅ Learning Outcomes

- Designed a real-world scalable LAN/WAN network.
- Implemented VLSM for efficient IP distribution.
- Configured RIP for dynamic routing.
- Gained hands-on experience with Cisco Packet Tracer tools.


