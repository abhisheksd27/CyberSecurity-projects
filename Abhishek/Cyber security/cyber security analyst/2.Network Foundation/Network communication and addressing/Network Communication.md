## 🖇️ MAC Address (Layer 2 – Data Link)

- **Definition** → Unique hardware ID tied to NIC (48-bit, hex format).
    
- **Structure** → First 24 bits = Manufacturer (OUI), last 24 bits = Device-specific.
    
- **Example** → `00:1A:2B:3C:4D:5E`.
    
- **Use** → Local communication in LAN, ensures data reaches correct device.
    
- **Tools** → `GETMAC` command in Windows.
    
- **Protocol Link** → ARP maps IP → MAC.
    
- **Flow Example** → Computer A (192.168.1.2) finds Computer B’s MAC (192.168.1.5 → `00:1A:2B:3C:4D:5F`) → Switch forwards frame to correct port.
    

## 🌍 IP Address (Layer 3 – Network)

- **Definition** → Logical address for devices in a network.
    
- **Versions** →
    
    - IPv4 → 32-bit, e.g., `192.168.1.1`.
        
    - IPv6 → 128-bit, e.g., `2001:0db8:85a3::7334`.
        
- **Use** → Routers use IPs to forward packets across networks.
    
- **Flexibility** → Can change (dynamic/static assignment).
    
- **Flow Example** → Router forwards packet based on destination IP.
    

## 🔢 Ports (Layer 4 – Transport)

- **Definition** → Numbers that identify services/processes on a device.
    
- **Range** → 0–65535.
    
- **Categories** →
    
    - **Well-Known (0–1023)** → Standard services (HTTP 80, HTTPS 443, FTP 20/21).
        
    - **Registered (1024–49151)** → Assigned to specific apps (SQL Server 1433).
        
    - **Dynamic/Private (49152–65535)** → Temporary client sessions (browser ephemeral ports).
        
- **Use** → Allow multiple services on one IP (e.g., web + email).
    
- **Tools** → `netstat` shows active ports.
    
- **Flow Example** → Browser → Server IP on port 80/443 → Server responds → Client uses dynamic port for session.
    

## 🌐 Browsing the Internet Example (Step-by-Step Flow)

1. **DNS Lookup** → Domain → IP (e.g., `example.com` → `93.184.216.34`).
    
2. **Encapsulation** → Browser creates HTTP request → TCP adds port (80/443) → IP adds destination → ARP finds router MAC.
    
3. **Transmission** → Frame sent to router MAC → Router forwards packet via IP → Intermediate routers continue.
    
4. **Server Processing** → Server receives packet → Directs to app listening on port 80/443 → Processes request.
    
5. **Response** → Server sends back to client’s dynamic port → Reverse path → Client receives webpage.
    

## 🖼️ Diagram Flow

Code

```
MAC Address (Layer 2) → Identifies device in LAN
IP Address (Layer 3) → Identifies device across networks
Port (Layer 4) → Identifies specific service/application
---------------------------------------------------------
Together → Ensure correct device + correct network + correct service
```

## 🎯 Key Takeaway

- **MAC** → Physical device ID (local).
    
- **IP** → Logical address (global).
    
- **Port** → Service identifier (application-level).
    
- All three work together to make sure data reaches the **right device, right network, right service**.