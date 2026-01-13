# Corporate Network: VLAN Segmentation and Inter-VLAN Routing

## 📌 Project Overview
This project demonstrates the implementation of a segmented local area network (LAN) for a corporate environment. Using a "Router-on-a-Stick" architecture, the network isolates departments into specific VLANs to enhance security, reduce broadcast domains, and organize traffic flow. All inter-VLAN communication is managed by a central router.

## 🚀 Technical Features
* **Departmental Segmentation:** Creation of specific VLANs for Finance, HR, and Sales departments.
* **Inter-VLAN Routing:** Configuration of subinterfaces on a Cisco 1941 router to bridge communication between different network segments.
* **IEEE 802.1Q Trunking:** Implementation of trunk links between Cisco 2960 switches and the 1941 router.
* **Network Hardware:** * 01 Cisco 1941 Integrated Services Router.
    * 02 Cisco Catalyst 2960 Series Switches.

## 📊 VLAN & Addressing Plan
| Device | VLAN ID | Department | Subnet | Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **Switch 1** | 10 | **FINANCE** | 192.168.10.0/24 | 192.168.10.1 |
| **Switch 1** | 20 | **HR** | 192.168.20.0/24 | 192.168.20.1 |
| **Switch 2** | 30 | **SALES** | 192.168.30.0/24 | 192.168.30.1 |

## ⚙️ Configuration Snippets (CLI)

### 1. VLAN Database Creation (Switch 1 & 2)
```bash
S1# configure terminal
S1(config)# vlan 10
S1(config-vlan)# name FINANCE
S1(config-vlan)# vlan 20
S1(config-vlan)# name HR
!
S2(config)# vlan 30
S2(config-vlan)# name SALES
```

2. Router-on-a-Stick Configuration (Router 1941)
```
R1(config)# interface gigabitEthernet 0/0.10
R1(config-subif)# encapsulation dot1Q 10
R1(config-subif)# ip address 192.168.10.1 255.255.255.0
!
R1(config)# interface gigabitEthernet 0/0.20
R1(config-subif)# encapsulation dot1Q 20
R1(config-subif)# ip address 192.168.20.1 255.255.255.0
!
R1(config)# interface gigabitEthernet 0/0.30
R1(config-subif)# encapsulation dot1Q 30
R1(config-subif)# ip address 192.168.30.1 255.255.255.0
```

🧪 Verification & Results
VLAN Database: Confirmed via show vlan brief on both switches, showing active status for FINANCE, HR, and SALES.

Trunking Protocol: Verified using show interfaces trunk to ensure 802.1Q encapsulation is active on inter-switch and router links.

Connectivity Test: Successful end-to-end ICMP (ping) tests between hosts in different VLANs, confirming operational routing.

Developed by [Eduardo]
