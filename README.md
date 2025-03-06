# OSPF-ABR-PacketTracer
A Cisco Packet Tracer project implementing OSPF with an Area Border Router (ABR) to connect multiple areas
# OSPF Area Border Router (ABR) in Cisco Packet Tracer

## 📌 Overview
This project demonstrates the **OSPF (Open Shortest Path First) routing protocol** using an **Area Border Router (ABR)** in Cisco Packet Tracer.

## 🖥️ Network Topology
- **R1 (ABR)** connects **Area 0 (Backbone) and Area 1**.
- **R2 (Internal Router in Area 0)**
- **R3 (Internal Router in Area 1)**
- **PCs connected via switches to R2 and R3**.

## ⚙️ Configuration Commands
Here are the key OSPF configuration commands used in the routers:

### **Router 1 (ABR - R1)**
```cisco
enable
configure terminal
hostname R1
interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
interface GigabitEthernet0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit
router ospf 1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.2.0 0.0.0.255 area 1
exit
write memory




enable
configure terminal
hostname R2
interface GigabitEthernet0/0
ip address 192.168.1.2 255.255.255.0
no shutdown
exit
interface GigabitEthernet0/1
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
router ospf 1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.10.0 0.0.0.255 area 0
exit
write memory


enable
configure terminal
hostname R3
interface GigabitEthernet0/0
ip address 192.168.2.2 255.255.255.0
no shutdown
exit
interface GigabitEthernet0/1
ip address 192.168.20.1 255.255.255.0
no shutdown
exit
router ospf 1
network 192.168.2.0 0.0.0.255 area 1
network 192.168.20.0 0.0.0.255 area 1
exit
write memory


