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

## ⚙️ Configuration (Basic)
vlan 10
name HR
vlan 20
name FINANCE
vlan 30
name IT

### Switch
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0


### Router


## 🚀 Result
Devices in different VLANs can communicate via routing.

## 📌 Use Case
Enterprise network segmentation
