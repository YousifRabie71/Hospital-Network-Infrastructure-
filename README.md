# Hospital Network Infrastructure Design & Simulation

A secure, campus-style network infrastructure designed and simulated for a three-floor healthcare facility using **Cisco Packet Tracer**. This project implements logical network segmentation, centralized traffic distribution, and static service configurations to meet strict healthcare requirements.

## Network Topology
Below is the logical network diagram showing the three floor-based subnets connected to the central core switch and hospital router.
<img width="1918" height="1078" alt="network-diagram" src="https://github.com/user-attachments/assets/dfb9f89a-1759-4ae7-9a60-f636bffa09dd" />

## Design & Configuration Details

###  Network Segmentation (VLANs)
The facility is logically divided floor-by-floor into three distinct Virtual Local Area Networks (VLANs) to minimize broadcast traffic and secure departmental data:
* **VLAN 10 (Ground Floor):** Reception systems, administrative PCs, and network printers (`192.168.10.0/24`).
* **VLAN 20 (First Floor):** Doctor's PCs, management cabins, and the central server room (`192.168.20.0/24`).
* **VLAN 30 (Second Floor):** Treatment units and nursing station systems (`192.168.30.0/24`).

###  Routing & Core Services
* **Inter-VLAN Routing:** Configured using the **Router-on-a-Stick** approach on the central Hospital Router via sub-interfaces (`fa0/0.10`, `fa0/0.20`, `fa0/0.30`) using 802.1Q encapsulation.
* **FTP Server Service:** Dedicated central server deployed on the first floor (`192.168.20.5`) with secure FTP profiles enabled to facilitate seamless administrative file sharing across subnets.

##  Verification & Testing
Network reliability and connectivity have been verified and confirmed with a **100% Pass Status** using the following tools inside Packet Tracer:
1. **ICMP Ping Testing:** End-to-end multi-subnet connectivity tests (e.g., Ground Floor PC1 to First Floor Server) confirmed 0% packet loss and low-latency response times.
2. **PDU Simulation Mode:** Visual step-by-step frame analysis across trunk links and sub-interfaces successfully passed all designated data routes.

##  How to Run the Project
1. Download and install **Cisco Packet Tracer**.
2. Download the `Hospital Network Project.pkt` file from this repository.
3. Open the file in Packet Tracer to explore the configurations or access the terminal on any host machine to test network pings.
