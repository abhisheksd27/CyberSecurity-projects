## 📚 Network Layer Basics

- **Role** → Controls exchange of data packets across networks.
    
- **Challenge** → Packets cannot go directly to receiver → must pass through routing nodes.
    
- **Functions** →
    
    1. **Logical Addressing** → Assigns unique addresses (IP).
        
    2. **Routing** → Determines best path from source → destination.
        
    3. **Flow Control** → Manages packet delivery, avoids congestion.
        

## 🔑 Protocols at Layer 3

- **IPv4 / IPv6** → Logical addressing, packet delivery.
    
- **IPsec** → Security (encryption/authentication of IP packets).
    
- **ICMP** → Error reporting & diagnostics (ping, traceroute).
    
- **IGMP** → Manages multicast group memberships.
    
- **RIP** → Distance-vector routing protocol.
    
- **OSPF** → Link-state routing protocol, efficient path selection.
    

## ⚙️ How It Works

1. Sender creates packet with **source & destination IP**.
    
2. Router checks routing table → forwards packet to next hop.
    
3. Packet travels **node to node** until destination is reached.
    
4. Intermediate nodes **do not process higher-layer data** → only forward based on IP.
    
5. Receiver decapsulates packet → passes data up to Transport Layer.
    

## 🖼️ Flow Diagram (Simplified)

Code

```
Sender → Router A → Router B → Router C → Receiver
(Packet hops node to node using Layer 3 addressing)
```

## 🎯 Key Takeaway

- **Layer 3 = “Post Office” of the network.**
    
- Ensures packets reach correct destination even across multiple subnets.
    
- Uses **logical addressing + routing tables**.
    
- Protocols like IPv4, ICMP, OSPF make routing reliable and secure.