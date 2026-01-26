# Enterprise Network & DHCP Infrastructure 🌐
**A robust Inter-VLAN routing and automated IP addressing solution for RH, VENDA, and FINANCEIRO departments.**

## 📌 Project Overview
This project simulates a real-world corporate scenario. I implemented a **Centralized DHCP Server** on a Cisco Router to automate network configuration for three specific departments: **RH (Human Resources)**, **VENDA (Sales)**, and **FINANCEIRO (Finance)**. By using the Router-on-a-Stick method, I ensured that these isolated VLANs can communicate securely through a single physical interface.

> **Architecture:** Router-on-a-Stick + Centralized DHCP Server ✅

## 📐 Network Topology
![Network Topology](01_logical_topology.png)
*Detailed topology showing the Router as the Gateway for RH, VENDA, and FINANCEIRO.*

## 🛠️ Tech Stack & Protocols
- **Tool:** Cisco Packet Tracer
- **Methodology:** Router-on-a-Stick (Inter-VLAN Routing)
- **DHCP Services:** Centralized Pools for each department
- **Encapsulation:** IEEE 802.1Q (Dot1Q)
- **Segmentation:** VLAN 10 (RH), VLAN 20 (VENDA), VLAN 30 (FINANCEIRO)
- **Verification:** ICMP (Ping) & IP Config analysis

## ⚙️ Configuration Highlights

### 1. Centralized DHCP Pools
The router manages three distinct pools to ensure each department stays in its subnet:
- **Pool RH:** `192.168.10.0/24`
- **Pool VENDA:** `192.168.20.0/24`
- **Pool FINANCEIRO:** `192.168.30.0/24`

### 2. Logical Segmentation (802.1Q)
Configured sub-interfaces on the main Router to handle traffic for all three VLANs, providing a scalable and cost-effective routing solution.

## 🧪 Proof of Success

### DHCP Addressing Verification
Verification of a host in the **FINANCEIRO** or **VENDA** department receiving its automated IP configuration from the Router.
![DHCP Verification](07_pcVLAN10_ip_configurationn.png) 
### End-to-End Connectivity (Inter-VLAN Ping)
Confirming that the **RH** department can reach the **FINANCEIRO** department through the gateway, proving the routing logic is flawless.
![Ping Test Result](09_test-ping_vlan10.png)
*Result: 0% packet loss and successful DHCP lease verification.*

## 📁 Repository Structure
- `/topology`: Cisco Packet Tracer source file (.pkt).
- `/print`: Screenshots of topology, DHCP leases, and connectivity tests.
- `README.md`: Project documentation.

---
**Developed by:** Eduardo Almeida  
**Date:** January 2026  
*Enterprise Networking, Automated Services, and Infrastructure Design.*
