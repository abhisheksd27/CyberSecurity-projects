## 📚 MAC Address Basics

- **Definition** → 48-bit (6 octets) physical address, unique to each network interface.
    
- **Format** → Hexadecimal (e.g., `DE:AD:BE:EF:13:37`).
    
- **Standards** → Ethernet (802.3), Bluetooth (802.15), WLAN (802.11).
    
- **Structure** →
    
    - **OUI (first 3 bytes)** → Manufacturer ID.
        
    - **NIC (last 3 bytes)** → Device-specific, ensures uniqueness.
        

## 🔑 MAC Address Types

- **Unicast** → Last bit = 0 → Packet sent to one host.
    
- **Multicast** → Last bit = 1 → Packet sent to multiple hosts.
    
- **Broadcast** → `FF:FF:FF:FF:FF:FF` → Sent to all devices in subnet.
    
- **Global vs Local** →
    
    - Global OUI → Assigned by IEEE.
        
    - Local → Manually set or spoofed.
        

## ⚠️ MAC Attack Vectors

1. **MAC Spoofing** → Change MAC to impersonate another device.
    
2. **MAC Flooding** → Overload switch MAC table → causes failover to broadcast mode.
    
3. **MAC Filtering Bypass** → Exploit networks that allow only specific MACs.
    

## 🛡️ ARP (Address Resolution Protocol)

- **Role** → Maps IP (Layer 3) → MAC (Layer 2).
    
- **Process** →
    
    - **ARP Request** → “Who has IP X? Tell me.” (broadcast).
        
    - **ARP Reply** → Device with IP responds with its MAC.
        
- **Example Capture**:
    
    - Request → `Who has 10.129.12.101? Tell 10.129.12.100`
        
    - Reply → `10.129.12.101 is at AA:AA:AA:AA:AA:AA`
        

## ⚠️ ARP Spoofing (Attack)

- **Method** → Attacker sends fake ARP replies, binding their MAC to gateway IP.
    
- **Result** → Victim sends traffic to attacker instead of gateway → MITM attack.
    
- **Tools** → Ettercap, Cain & Abel.
    
- **Defense** →
    
    - Use secure protocols (IPSec, SSL/TLS).
        
    - Firewalls + IDS/IPS.
        
    - Dynamic ARP inspection on switches.
        

## 🖼️ Flow Diagram (Simplified)

Code

```
Normal:
Host A → ARP Request → Broadcast
Host B → ARP Reply → MAC Address
Communication → Direct via MAC

Spoofed:
Attacker → Fake ARP Reply → Victim
Victim → Sends traffic → Attacker’s MAC
Attacker → Intercepts/forwards → Gateway
```

## 🎯 Key Takeaway

- **MAC = Hardware identity, unique per NIC.**
    
- **ARP = Resolves IP → MAC for local delivery.**
    
- **Unicast, Multicast, Broadcast** → Define packet delivery scope.
    
- **Attack Risks** → MAC spoofing, flooding, ARP poisoning.
    
- **Defense** → Layered security, monitoring, secure protocols.