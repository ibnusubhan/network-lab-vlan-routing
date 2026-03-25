# 📡 Enterprise Network Lab: VLAN, DHCP & Inter-VLAN Routing

🚀 Hands-on network lab simulating real enterprise environment

## 🌍 Overview
This project simulates a small enterprise network using VLAN segmentation and routing.
This project demonstrates VLAN segmentation, inter-VLAN routing, and DHCP implementation in a simulated enterprise environment.

## 🖼 Topology
![Topology](topology.png)
Topology created using Cisco Packet Tracer

## 🧰 Tools
- Cisco Packet Tracer
- CLI (Command Line Interface)

## 🧠 Network Design
- 3 VLANs (HR, Finance, IT)
- Inter-VLAN Routing using Router

## 📊 VLAN Table
| VLAN | Department | IP |
|------|----------|------|
| 10 | HR | 192.168.10.0/24 |
| 20 | Finance | 192.168.20.0/24 |
| 30 | IT | 192.168.30.0/24 |

## ⚙️ Configuration

### 🔹 Switch Configuration
```bash
conf t
vlan 10
name HR
vlan 20
name FINANCE
vlan 30
name IT

interface fa0/1
switchport mode access
switchport access vlan 10

interface fa0/2
switchport mode access
switchport access vlan 20

interface fa0/3
switchport mode access
switchport access vlan 30

interface fa0/24
switchport mode trunk
```

### 🔹 Router Configuration
```bash
conf t
interface g0/0
no shutdown

interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0

interface g0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0
```


### 🔹 Router DHCP Configuration
```bash
ip dhcp excluded-address 192.168.10.1
ip dhcp excluded-address 192.168.20.1
ip dhcp excluded-address 192.168.30.1

ip dhcp pool VLAN10
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8

ip dhcp pool VLAN20
network 192.168.20.0 255.255.255.0
default-router 192.168.20.1
dns-server 8.8.8.8

ip dhcp pool VLAN30
network 192.168.30.0 255.255.255.0
default-router 192.168.30.1
dns-server 8.8.8.8
```

## 🧪 Testing

### DHCP Test
- PCs successfully receive IP automatically

### Connectivity Test
- Ping between VLANs: SUCCESS
- Gateway reachable from all VLANs

## 📡 Key Features
- VLAN segmentation for network isolation
- Inter-VLAN routing using Router-on-a-Stick
- Dynamic IP assignment using DHCP


## 🚀 Result
- VLAN segmentation successfully implemented
- Inter-VLAN routing working correctly
- DHCP server assigns IP automatically
- Full connectivity between VLANs verified

## 📌 Use Case
Enterprise network segmentation
