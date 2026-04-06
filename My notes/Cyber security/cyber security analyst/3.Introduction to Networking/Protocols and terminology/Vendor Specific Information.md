## 📚 Cisco IOS Basics

- **Operating System** for Cisco routers/switches.
    
- **Features** → IPv6 support, QoS, encryption/authentication, VRF, VPLS.
    
- **Management** → CLI (most common), GUI, remote via SSH/Telnet.
    
- **Protocols Supported** →
    
    - Routing: OSPF, BGP.
        
    - Switching: VTP, STP.
        
    - Services: DHCP.
        
    - Security: ACLs.
        

## 🔑 Password Types in IOS

|Password Type|Purpose|
|---|---|
|User|Login to IOS.|
|Enable|Access to enable mode.|
|Secret|Restrict access to functions/services.|
|Enable Secret|Encrypted, secure access to enable mode.|

## 🏷️ VLANs (Virtual LANs)

- **Definition** → Logical segmentation of a switch into multiple broadcast domains.
    
- **Benefits** → Organization, security, simplified admin, performance.
    
- **Range** → VLAN IDs 1–4094 (0 & 4095 reserved).
    
    - Normal range: 1–1005 (stored in vlan.dat).
        
    - Extended range: 1006–4094 (not saved in vlan.dat).
        
- **Example Segmentation**:
    
    - Servers → VLAN 10 → 192.168.1.0/24
        
    - Finance → VLAN 30 → 192.168.3.0/24
        
    - HR → VLAN 40 → 192.168.4.0/24
        

## 🔑 VLAN Membership

- **Static VLANs** → Ports manually assigned (more secure).
    
- **Dynamic VLANs** → Based on MAC/protocol via VMPS (flexible but vulnerable to spoofing).
    

## 🔑 Access vs Trunk Ports

- **Access Port** → Carries traffic for one VLAN.
    
- **Trunk Port** → Carries multiple VLANs (switch ↔ switch/router).
    

## 🖼️ VLAN Identification

- **ISL (Cisco proprietary)** → Deprecated.
    
- **802.1Q (IEEE standard)** → Adds VLAN tag (TPID = 0x8100, TCI fields).
    
- **Double Tagging** → Multiple VLAN tags in one frame (used legitimately by ISPs, exploitable in attacks).
    

## 🛠️ VLAN NIC Configuration

- **Linux** → `ip link add link eth0 name eth0.20 type vlan id 20` → creates VLAN interface.
    
- **Windows** → Device Manager → VLAN ID property OR PowerShell (`Set-NetAdapter -Name "Ethernet 2" -VlanID 10`).
    

## 📡 VLAN Traffic Analysis

- **Wireshark** → Filter `vlan` or `vlan.id == 10`.
    
- **Tshark** → Extract VLAN IDs from PCAP (`tshark -r file.pcapng -T fields -e vlan.id`).
    

## ⚠️ VLAN Attacks

1. **VLAN Hopping (DTP abuse)** → Attacker mimics switch, negotiates trunk, gains access to multiple VLANs.
    
    - Tool: Yersinia.
        
2. **Double-Tagging Attack** → Hidden VLAN tag inside another → packet forwarded to unintended VLAN.
    
    - Tools: Scapy, Yersinia.
        

## 🌍 VXLAN (Virtual eXtensible LAN)

- **Problem** → VLAN limit = 4094 IDs, STP limitations.
    
- **Solution** → VXLAN (RFC 7348) → Layer 2 overlay on Layer 3.
    
- **Features** →
    
    - 24-bit VNI → ~16 million segments.
        
    - Scalable across data centers.
        
    - Designed for cloud & virtualized environments.
        

## 🔑 Cisco Discovery Protocol (CDP)

- Layer 2 protocol → Cisco devices discover neighbors.
    
- Provides → Device ID, IP, Port, Capabilities, IOS version, Platform.
    
- **Security Note** → Often enabled by default, but can be disabled.
    

## 🔑 Spanning Tree Protocol (STP)

- Prevents loops in Ethernet networks.
    
- Parameters → Root ID, MAC, Port ID, Hello Time, Forward Delay.
    
- Variants → Rapid STP (802.1w).
    

## 🎯 Key Takeaway

- **Cisco IOS** → Core OS for routers/switches, supports routing, switching, security.
    
- **VLANs** → Logical segmentation, improve security/performance, but vulnerable to hopping/double-tagging.
    
- **VXLAN** → Modern scalable solution for cloud/data centers.
    
- **CDP/STP** → Essential Layer 2 protocols (discovery vs loop prevention).