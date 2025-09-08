# University Campus Network 

## 📌 Project Overview
This project simulates the **University Network Infrastructure** using **Cisco Packet Tracer**. Albion University has **two campuses** located 20 miles apart:  
- **Main Campus** – Hosts Administrative departments, Faculties (Business, Engineering/Computing, Art & Design), IT Department, and Student Labs.  
- **Branch Campus(Small Campus)** – Hosts the Faculty of Health & Sciences with separate networks for staff and students.  

The objective was to design and configure a **scalable, secure, and functional campus network** following hierarchical network design principles and Cisco CCNA concepts.  

---

## 🏫 Network Case Study & Requirements
- **Main Campus**  
  - **Building A:** Administrative staff (Management, HR, Finance) and Faculty of Business. Shared networking equipment with VLAN segmentation.  
  - **Building B:** Faculty of Engineering & Computing (E&C) and Faculty of Art & Design (A&D).  
  - **Building C:** Student labs and IT Department (hosts internal servers such as Web server).  

- **Branch Campus**  
  - **Faculty of Health & Sciences (H&S):** Separate VLANs and networks for staff and students.  

- **External Connectivity**  
  - Email Server hosted in the **Cloud**.  
  - Routers use **RIPv2** for dynamic routing internally and **Static Routing** for external cloud server access.  

- **General Requirements**  
  - Each department/faculty on its own IP subnet.  
  - VLANs and port security implemented on switches.  
  - DHCP for dynamic IP allocation in Building A.  
  - Inter-VLAN routing via Router-on-a-Stick.  
  - SSH for secure remote device management.  

---

## 🖥️ Technologies Implemented
1. **Cisco Packet Tracer** for network design and simulation.  
2. **Hierarchical Network Design** – Core, Distribution, and Access layers.  
3. **Correct Cabling** (straight-through, cross-over, and fiber links).  
4. **VLAN Creation & Assignment** to departments.  
5. **Subnetting & IP Addressing** for staff, students, and servers.  
6. **Inter-VLAN Routing (Router-on-a-Stick)** for communication across VLANs.  
7. **Router as DHCP Server** for dynamic addressing.  
8. **RIPv2 Protocol** for intra-campus routing.  
9. **Static Routing** for external email server access.  
10. **SSH Configuration** for secure device management.  
11. **Switch Port Security** to prevent unauthorized device access.  
12. **Server Configurations** – Internal Web Server & Cloud Email Server.  

---

## 📡 Additional Functionalities
Beyond the requirements, additional wireless functionality was added:  
- **Building A (Admin):** Wireless Access Point for staff mobile devices and laptops.  
- **Building C (IT Lab):** Access Point for students’ laptops.  
- **Branch Campus (Staff):** Wireless AP for faculty/staff laptops.  

This ensures **mobility and flexible network access** for staff and students.  

---

## 📊 VLAN & IP Addressing Scheme

| VLAN | Subnet          | Department/Faculty          | Location       |
|------|----------------|-----------------------------|---------------|
| 10   | 192.168.1.0/24 | Admin                       | Building A    |
| 20   | 192.168.2.0/24 | HR                          | Building A    |
| 30   | 192.168.3.0/24 | Finance                     | Building A    |
| 40   | 192.168.4.0/24 | Business                    | Building A    |
| 50   | 192.168.5.0/24 | Engineering & Computing     | Building B    |
| 60   | 192.168.6.0/24 | Art & Design                | Building B    |
| 70   | 192.168.7.0/24 | Student Labs                | Building C    |
| 80   | 192.168.8.0/24 | IT Department + Servers     | Building C    |
| 90   | 192.168.9.0/24 | Health & Sciences Staff     | Branch Campus |
| 100  | 192.168.10.0/24| Health & Sciences Students  | Branch Campus |

---

## ⚙️ Implementation Process

### **1. Device Setup & Cabling**
- Placed routers, switches, PCs, laptops, servers, and access points in Packet Tracer.  
- Used correct cabling: straight-through for PCs-to-switch, cross-over for switch-to-switch, fiber for backbone links.  

### **2. VLAN Configuration**
- Created VLANs on all switches (10, 20, 30 … 100).  
- Assigned switch ports to corresponding VLANs based on department.  
- Configured trunk links between switches and routers.  

### **3. Subnetting & IP Addressing**
- Designed subnets for each department based on /24 addressing.  
- Assigned default gateways (router sub-interfaces for Router-on-a-Stick).  
- Configured servers with static IP addresses.  

### **4. Inter-VLAN Routing (Router-on-a-Stick)**
- Configured router sub-interfaces with encapsulation dot1q for each VLAN.  
- Assigned IP addresses as gateways.  

### **5. DHCP Configuration**
- Configured the Main Campus Router as a DHCP server.  
- Created DHCP pools for departments in **Building A** (Admin, HR, Finance, Business).  
- Excluded gateway and server addresses.  

### **6. Routing**
- Enabled **RIPv2** on routers for dynamic routing between campuses.  
- Configured **Static Routes** for external Email Server in the Cloud.  

### **7. Wireless Configuration**
- Deployed Access Points in Admin, IT Lab, and Branch Staff areas.  
- Configured SSIDs and connected laptops/smartphones.  

### **8. Security**
- Configured **SSH** on routers and switches for remote access.  
- Enabled **port-security** on access ports (limited MAC addresses, sticky MAC).  

### **9. Testing & Verification**
- Verified DHCP leases with PCs in Building A.  
- Tested **ping & traceroute** across VLANs and campuses.  
- Verified wireless connectivity with laptops and smartphones.  
- Checked **RIP routing tables** with `show ip route`.  
- Verified SSH login from Admin PC to Router/Switch.  
- Ensured Cloud Email Server communication via static route.  

---

## ✅ Testing & Results
- **Inter-VLAN communication:** Success.  
- **DHCP allocation in Building A:** Success.  
- **SSH remote access:** Success.  
- **RIP routing tables exchanged:** Success.  
- **Wireless laptop/smartphone access:** Success.  
- **Connectivity with Cloud Email Server:** Success.  

---

## 🗺️ Network Topology

![ University Network Topology](./Campus%20netwrok.png)
---

## 🚀 Conclusion
This project demonstrates a **fully functional, secure, and scalable university network** using CCNA-level technologies. It integrates:  
- **VLANs, Inter-VLAN Routing, DHCP, RIPv2, Static Routing, SSH, Port-Security, and Wireless Access**.  
- Provides both **wired and wireless access** across two campuses.  
- Ensures **future scalability and practical real-world design**.  
