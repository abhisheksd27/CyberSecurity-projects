## 🌍 IP Address Basics

- **Public IP** → Globally unique, assigned by ISP, routable on Internet.
    
    - Example: `8.8.8.8` (Google DNS).
        
- **Private IP** → Used inside LANs, not routable on Internet.
    
    - Ranges: `10.x.x.x`, `172.16.x.x – 172.31.x.x`, `192.168.x.x`.
        
- **Problem** → IPv4 has only ~4.3 billion addresses → shortage.
    
- **Solution** → NAT allows multiple private IPs to share one public IP.
    

## 🔄 What is NAT?

- **Definition** → Router modifies source/destination IPs in packet headers.
    
- **Purpose** → Translate private IPs → public IP for Internet access.
    
- **Security Benefit** → Internal devices hidden from direct exposure.
    

## ⚙️ How NAT Works (Example)

- Devices in LAN:
    
    - Laptop → `192.168.1.10`
        
    - Smartphone → `192.168.1.11`
        
    - Console → `192.168.1.12`
        
- Router:
    
    - LAN IP → `192.168.1.1`
        
    - WAN/Public IP → `203.0.113.50`
        
- Flow:
    
    1. Laptop sends request → Source IP `192.168.1.10`.
        
    2. Router translates → Public IP `203.0.113.50`.
        
    3. Server responds → Router maps back using NAT table (IP + port).
        
    4. Router forwards response → Laptop receives data.
        

## 🧩 Types of NAT

1. **Static NAT** → One-to-one mapping (private ↔ public).
    
2. **Dynamic NAT** → Public IP assigned from pool as needed.
    
3. **PAT (Port Address Translation)** → Many private IPs share one public IP using port numbers.
    
    - Most common in homes/offices.
        

## ✅ Benefits

- Conserves IPv4 address space.
    
- Adds basic security (internal devices hidden).
    
- Flexible internal addressing.
    

## ⚠️ Trade-Offs

- Hosting servers behind NAT needs port forwarding.
    
- Breaks some protocols needing end-to-end connectivity.
    
- Troubleshooting becomes more complex.
    

## 🖼️ Flow Diagram (NAT)

Code

```
Private LAN (192.168.1.x)
   |
   v
Router with NAT (Public IP 203.0.113.50)
   |
   v
Internet (Remote Server 503.0.135.60)
```

## 🎯 Key Takeaway

- **NAT = Bridge between private and public IPs.**
    
- **Allows many devices to share one public IP.**
    
- **Most common form = PAT (NAT Overload).**
    
- **Essential for IPv4 conservation + basic security.**