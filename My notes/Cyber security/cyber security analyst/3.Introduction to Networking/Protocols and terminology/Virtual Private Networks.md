## 📚 VPN Basics

- **Definition** → Secure, encrypted tunnel between remote device ↔ private network.
    
- **Purpose** → Remote access to internal servers/resources securely.
    
- **Ports** →
    
    - PPTP → TCP/1723
        
    - IKEv1/v2 → UDP/500
        
- **Benefits** →
    
    - Encrypts communication (confidentiality).
        
    - Enables remote work (home/travel).
        
    - Cost-effective (uses public Internet vs leased lines).
        
    - Connects multiple branch offices into one private network.
        

## 🔑 VPN Components

|Component|Description|
|---|---|
|VPN Client|Installed on remote device (e.g., OpenVPN client).|
|VPN Server|Accepts connections, routes traffic.|
|Encryption|AES, IPsec secure the tunnel.|
|Authentication|Shared secret, certificates, or other methods.|

## 🛡️ IPsec (Internet Protocol Security)

- Provides **encryption + authentication** for IP packets.
    
- **Protocols**:
    
    - **AH (Authentication Header)** → Integrity + authenticity, no encryption.
        
    - **ESP (Encapsulating Security Payload)** → Encryption + optional authentication.
        
- **Modes**:
    
    - **Transport Mode** → Encrypts payload only (end-to-end host communication).
        
    - **Tunnel Mode** → Encrypts entire packet (used for VPN tunnels).
        

**Firewall Requirements for IPsec VPN traffic**:

- UDP/50–51 → IP protocols.
    
- UDP/500 → IKE (key exchange).
    
- UDP/4500 → ESP (encrypted traffic).
    

## ⚠️ PPTP (Point-to-Point Tunneling Protocol)

- Encapsulates PPP traffic into IP tunnel.
    
- **Weaknesses** → Uses MSCHAPv2 with DES encryption → easily cracked.
    
- **Status** → Deprecated, replaced by L2TP/IPsec, IKEv2, OpenVPN.
    

## 🖼️ Flow Diagram (Simplified)

Code

```
Remote Device → VPN Client → Internet → VPN Server → Private Network
   | Encryption (AES/IPsec)
   | Authentication (Certificates/Shared Keys)
```

## 🎯 Key Takeaway

- **VPN = secure remote access** via encrypted tunnel.
    
- **IPsec = backbone of secure VPNs** (AH + ESP, Transport vs Tunnel mode).
    
- **PPTP = obsolete, insecure** → avoid in modern setups.
    
- **Ports (1723, 500, 4500)** are critical for VPN traffic.
    
- VPNs are essential for remote work, branch office connectivity, and secure administration.