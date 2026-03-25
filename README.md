# 📡 Network Lab: VLAN & Inter-VLAN Routing

## 🌍 Overview
This project simulates a small enterprise network using VLAN segmentation and routing.

## 🧠 Topology
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


### 🔹 Router Configuration
conf t
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0

interface g0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0


## 🚀 Result
- Successful VLAN segmentation
- Inter-VLAN communication working
- Devices can ping across VLANs

## 📌 Use Case
Enterprise network segmentation
