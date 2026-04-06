## 📚 TCP/IP Model (4 Layers)

1. **Application Layer (Layer 4)**
    
    - Provides services directly to applications.
        
    - Defines protocols for data exchange (HTTP, FTP, DNS, SMTP).
        
2. **Transport Layer (Layer 3)**
    
    - Ensures reliable communication between hosts.
        
    - **TCP** → Connection-oriented, error-checking, sequencing.
        
    - **UDP** → Connectionless, faster, no reliability guarantees.
        
3. **Internet Layer (Layer 2)**
    
    - Handles logical addressing, packaging, and routing.
        
    - Protocols: **IP**, **ICMP**.
        
    - Ensures packets reach the correct destination network.
        
4. **Link Layer (Layer 1)**
    
    - Places packets on the physical medium (Ethernet, Wi-Fi).
        
    - Deals with MAC addresses, frame formats, and hardware transmission.
        

## 🔑 Core Tasks of TCP/IP

|Task|Protocol|Description|
|---|---|---|
|Logical Addressing|IP|Structures networks via subnetting, CIDR, classes.|
|Routing|IP|Determines next hop for packet delivery.|
|Error & Control Flow|TCP|Maintains connection, checks reliability.|
|Application Support|TCP/UDP|Ports distinguish applications/services.|
|Name Resolution|DNS|Converts FQDNs (e.g., www.example.com) → IP addresses.|

## ⚙️ Encapsulation in TCP/IP

- **Application Data** → HTTP request.
    
- **Transport Layer** → TCP segment (adds source/destination ports).
    
- **Internet Layer** → IP packet (adds source/destination IPs).
    
- **Link Layer** → Frame (adds MAC addresses).
    
- **Physical Medium** → Bits transmitted.
    

**Receiver** → Reverses process (decapsulation) until application data is usable.

## 🖼️ OSI vs TCP/IP Comparison

|OSI Model (7 Layers)|TCP/IP Model (4 Layers)|PDU (Protocol Data Unit)|
|---|---|---|
|Application|Application|Data|
|Presentation|Application|Data|
|Session|Application|Data|
|Transport|Transport|Segment/Datagram|
|Network|Internet|Packet|
|Data-Link|Link|Frame|
|Physical|Link|Bit|

## 🎯 Key Takeaway

- **TCP/IP** → Practical, 4 layers, backbone of the Internet.
    
- **OSI** → Reference model, 7 layers, detailed analysis.
    
- **Encapsulation/Decapsulation** → Core process of data transfer.
    
- **Protocols** → TCP ensures reliability, IP ensures addressing/routing, DNS ensures name resolution.