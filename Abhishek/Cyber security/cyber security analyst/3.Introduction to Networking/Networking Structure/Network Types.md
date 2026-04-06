## 📚 Common Terminology

- **WAN (Wide Area Network)** → Internet, or large interconnected LANs.
    
- **LAN (Local Area Network)** → Internal networks (home, office).
    
- **WLAN (Wireless LAN)** → LAN over Wi-Fi.
    
- **VPN (Virtual Private Network)** → Extends/joins networks securely.
    

## 🌍 WAN

- **Definition** → Large-scale network (Internet or Intranet).
    
- **Identification** → Uses WAN routing protocols (BGP).
    
- **IP Schema** → Non-RFC 1918 addresses (public IPs).
    

## 🏠 LAN / WLAN

- **LAN** → Local internal network, usually RFC 1918 IP ranges.
    
- **WLAN** → Same as LAN but wireless.
    
- **Note** → Some institutions may assign routable IPs directly.
    

## 🔐 VPN Types

1. **Site-to-Site VPN** → Connects entire networks (routers/firewalls).
    
    - Example: Company offices linked securely over Internet.
        
2. **Remote Access VPN** → Client PC creates virtual interface.
    
    - Example: HackTheBox OpenVPN (TUN adapter).
        
    - **Split-Tunnel VPN** → Routes only specific networks, Internet bypasses VPN.
        
3. **SSL VPN** → Browser-based, streams apps/desktops.
    
    - Example: HackTheBox Pwnbox.
        

## 📖 Book Terms

- **GAN (Global Area Network)** → Worldwide networks (Internet, undersea cables, satellites).
    
- **MAN (Metropolitan Area Network)** → Regional, connects multiple LANs with fiber, leased lines.
    
- **PAN (Personal Area Network)** → Small, cable-based, ad hoc (few meters).
    
- **WPAN (Wireless PAN)** → Bluetooth, Wireless USB, ZigBee, Z-Wave (IoT, smart homes).
    

## 🖼️ Flow Diagram (Network Types)

Code

```
PAN/WPAN → LAN/WLAN → MAN → WAN → GAN
(Very small → local → regional → global)
```

## 🎯 Key Takeaway

- **LAN/WLAN** → Local, internal networks.
    
- **WAN** → Internet or large interconnected LANs.
    
- **VPN** → Securely extends networks.
    
- **Book Terms (GAN, MAN, PAN/WPAN)** → Good for exams, less common in daily use.
    
- **Hierarchy** → PAN → LAN → MAN → WAN → GAN.