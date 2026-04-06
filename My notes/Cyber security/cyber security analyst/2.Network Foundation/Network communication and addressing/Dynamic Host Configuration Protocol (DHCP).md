## 📚 DHCP Basics

- **Definition** → Automates IP address assignment in networks.
    
- **Purpose** → Avoids manual configuration, reduces errors, prevents IP conflicts.
    
- **Provides** → IP address, subnet mask, default gateway, DNS servers.
    
- **Lease** → IPs are temporary, must be renewed after expiry.
    

## 🧩 Roles

- **DHCP Server** → Router or dedicated server managing IP pool.
    
- **DHCP Client** → Any device requesting IP (PC, phone, laptop).
    

## ⚙️ DHCP Process (DORA)

1. **Discover** → Client broadcasts request for DHCP server.
    
2. **Offer** → Server replies with available IP + config.
    
3. **Request** → Client accepts offered IP.
    
4. **Acknowledge** → Server confirms assignment → Client can use IP.
    

**Lease Renewal** → Client sends DHCP Request before expiry → Server responds with Acknowledge to extend lease.

## 🖼️ Flow Diagram (DORA)

Code

```
Client → DHCP Discover → Server
Server → DHCP Offer → Client
Client → DHCP Request → Server
Server → DHCP Acknowledge → Client
```

## 📑 Example Scenario

- Alice connects laptop → Sends **Discover**.
    
- Server offers IP `192.168.1.10`.
    
- Laptop requests IP → Server acknowledges.
    
- Laptop now uses `192.168.1.10`.
    
- After 24h lease → Laptop must renew → Request + Acknowledge again.
    

## 🎯 Key Takeaway

- **DHCP = Automated IP assignment**.
    
- **DORA = Discover, Offer, Request, Acknowledge**.
    
- **Lease system** ensures efficient use of IP pool.
    
- Simplifies management in **large networks**.