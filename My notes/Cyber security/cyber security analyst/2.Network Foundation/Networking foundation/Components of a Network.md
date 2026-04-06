## 🖥️ End Devices

- **Definition** → Devices that send/receive data (hosts).
    
- **Examples** → Computers, smartphones, tablets, IoT devices, smart TVs.
    
- **Role** → Data generation & consumption (browsing, streaming, messaging).
    
- **Connection** → Wired (Ethernet) or Wireless (Wi-Fi).
    
- **Analogy** → Student using a laptop to connect to school Wi-Fi.
    

## 🔗 Intermediary Devices

- **Definition** → Devices that connect/manage traffic between end devices/networks.
    
- **Examples** → Routers, switches, modems, access points.
    
- **Functions** → Packet forwarding, routing, traffic management, security (firewalls).
    
- **OSI Layers** → Routers (Layer 3), Switches (Layer 2).
    
- **Analogy** → Home router connecting all devices to ISP.
    

## 🧩 Network Interface Cards (NICs)

- **Definition** → Hardware enabling device-to-network connection.
    
- **Unique ID** → MAC address.
    
- **Types** → Wired NIC (Ethernet), Wireless NIC (Wi-Fi).
    
- **Example** → Desktop with Ethernet NIC, laptop with Wi-Fi NIC.
    

## 🌐 Routers

- **Role** → Forward packets between networks (Layer 3).
    
- **Uses** → Routing tables, protocols (OSPF, BGP).
    
- **Functions** → Traffic management, security (ACLs, firewalls).
    
- **Example** → Home router connecting devices to ISP.
    

## 🔀 Switches

- **Role** → Connect devices within LAN (Layer 2).
    
- **Uses** → MAC addresses for forwarding.
    
- **Benefit** → Reduces congestion, improves performance.
    
- **Example** → Office switch connecting PCs, printers, servers.
    

## 📡 Hubs

- **Role** → Basic device, broadcasts data to all ports (Layer 1).
    
- **Drawback** → Inefficient, collisions.
    
- **Status** → Outdated, replaced by switches.
    

## 🧵 Network Media & Software

- **Media** → Cables (Ethernet, fiber), wireless signals (Wi-Fi, Bluetooth).
    
- **Software** → Protocols (TCP/IP, HTTP, FTP), management tools, firewalls.
    
- **Function** → Define rules, monitor performance, enhance security.
    

## 🔌 Cabling & Connectors

- **Examples** → Ethernet cables, fiber optics, RJ-45 connectors.
    
- **Impact** → Quality affects speed, reliability.
    
- **Example** → Office PCs connected to switches via Ethernet + RJ-45.
    

## 📑 Network Protocols

- **Definition** → Rules for data formatting, transmission, error checking.
    
- **Examples** →
    
    - TCP/IP → Internet backbone.
        
    - HTTP/HTTPS → Web traffic.
        
    - FTP → File transfers.
        
    - SMTP → Email.
        

## 🛠️ Network Management Software

- **Functions** → Performance monitoring, configuration, fault analysis, security.
    
- **Example** → IT team monitoring company network traffic, updating devices.
    

## 🔥 Software Firewalls

- **Definition** → Device-level security application.
    
- **Role** → Block unauthorized traffic, restrict suspicious apps.
    
- **Example** → Windows/Linux built-in firewalls (IPTables).
    

## 🖥️ Servers

- **Definition** → Powerful computers providing services to clients.
    
- **Types** → Web, file, mail, database servers.
    
- **Functions** → Resource sharing, data management, authentication.
    
- **Model** → Client-Server (server responds to client requests).
    
- **Example** → Web server delivering a webpage to your browser.
    

## 🖼️ Flow Diagram (Network Components)

Code

```
End Devices (PCs, Phones, IoT)
        |
        v
Intermediary Devices (Routers, Switches, Modems, APs)
        |
        v
Network Media (Cables, Wi-Fi, Fiber) + NICs
        |
        v
Servers (Web, Mail, File, Database)
```

## 🎯 Key Takeaway

- **End Devices** → User interface.
    
- **Intermediary Devices** → Connect/manage traffic.
    
- **NICs + Media** → Enable communication.
    
- **Servers** → Provide services/resources.