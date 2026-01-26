# Corporate Network Segmentation 🌐
**A reliable Inter-VLAN routing solution using the "Router-on-a-Stick" architecture for department-level connectivity.**

## 📌 Project Overview
This project simulates a common corporate scenario where different departments (HR, Sales, and IT) need to be isolated in their own **VLANs** for security and performance, but still require a way to communicate. Using a single Cisco Router and Trunking protocols, I implemented a robust routing path between these segments.

> **Architecture:** Router-on-a-Stick (Inter-VLAN Routing) ✅

## 📐 Network Topology
![Network Topology](./print/01_Topology_Overview.png)
*Topology showing the central Router acting as the Gateway for multiple VLAN-segmented Switches.*

## 🛠️ Tech Stack & Protocols
- **Tool:** Cisco Packet Tracer
- **Methodology:** Router-on-a-Stick
- **Encapsulation:** IEEE 802.1Q (Dot1Q)
- **VLANs:** 10 (HR), 20 (Sales), 30 (IT Support)
- **Trunking:** Trunk mode links between Switches and Router
- **Testing:** ICMP (Ping) verification

## ⚙️ Configuration Highlights

### 1. VLAN Segmentation
Each department is isolated in its own broadcast domain:
- **VLAN 10 (HR):** `192.168.10.0/24`
- **VLAN 20 (Sales):** `192.168.20.0/24`
- **VLAN 30 (IT):** `192.168.30.0/24`

### 2. Router Sub-Interfaces
The Router's physical interface was divided into logical **Sub-interfaces** (e.g., `G0/0.10`), each acting as the Default Gateway for its respective VLAN.

## 🧪 Connectivity & Proof of Success

### Cross-Department Ping
The ultimate test: a host from the **HR** department successfully communicating with the **IT Support** department.
![Ping Test Result](./print/02_Ping_Test_Success.png)
*Result: 0% packet loss, confirming the Router is correctly switching traffic between sub-interfaces.*

### Host IP Configuration
Verification of the static IP scheme and the correct Default Gateway for each segment.
![IP Configuration Proof](./print/03_IP_Configuration_Verification.png)

## 📁 Repository Structure
- `/topology`: Cisco Packet Tracer source file (.pkt).
- `/print`: Screenshots of the environment and verification tests.
- `README.md`: Project documentation.

---
**Developed by:** Eduardo Almeida  
**Date:** January 2026  
*Focused on Infrastructure, Connectivity, and Network Security.*
