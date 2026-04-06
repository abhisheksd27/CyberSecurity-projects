![[Pasted image 20260310022149.png]]

![[Pasted image 20260310022228.png]]
![[Pasted image 20260310022235.png]]

## 📚 OSI Model (7 Layers)

1. **Application** → User interface (HTTP, FTP, SMTP).
    
2. **Presentation** → Data formatting, encryption, compression.
    
3. **Session** → Establish/maintain/terminate sessions.
    
4. **Transport** → Reliable delivery (TCP/UDP, segmentation).
    
5. **Network** → Logical addressing & routing (IP).
    
6. **Data-Link** → MAC addressing, framing, error detection.
    
7. **Physical** → Bits on wire (cables, signals).
    

## 🌍 TCP/IP Model (4 Layers)

1. **Application** → Combines OSI’s Application + Presentation + Session.
    
    - Protocols: HTTP, FTP, DNS, SMTP.
        
2. **Transport** → End-to-end communication.
    
    - Protocols: TCP, UDP.
        
3. **Internet** → Routing & addressing.
    
    - Protocols: IP, ICMP.
        
4. **Link** → Physical + Data-Link combined.
    
    - Ethernet, Wi-Fi, ARP.
        

## 🔄 Comparison Table

|OSI Model (7 Layers)|TCP/IP Model (4 Layers)|PDU (Protocol Data Unit)|
|---|---|---|
|Application|Application|Data|
|Presentation|Application|Data|
|Session|Application|Data|
|Transport|Transport|Segment/Datagram|
|Network|Internet|Packet|
|Data-Link|Link|Frame|
|Physical|Link|Bit|

## ⚙️ Packet Transfer (Encapsulation)

- **Sender Side** → Data moves down layers, each adds a **header**.
    
    - Application → Transport → Internet → Link → Physical.
        
- **Receiver Side** → Data moves up layers, each **removes header**.
    
    - Physical → Link → Internet → Transport → Application.
        
- **Process** → Encapsulation (add headers) → Transmission → Decapsulation (remove headers).
    

**Example (Browsing a Website)**

- Browser creates HTTP request (Application).
    
- TCP adds ports (Transport).
    
- IP adds source/destination IP (Internet).
    
- Ethernet/Wi-Fi adds MAC addresses (Link).
    
- Sent as bits (Physical).
    
- Server reverses process → sends response back.
    

## 🎯 Key Takeaway

- **OSI** → Detailed, 7 layers, strict reference model.
    
- **TCP/IP** → Practical, 4 layers, Internet backbone.
    
- **Encapsulation/Decapsulation** → Core process of data transfer.
    
- **For Pentesters** →
    
    - TCP/IP → Quick understanding of connections.
        
    - OSI → Detailed traffic analysis (packet captures, IDS/IPS).