## 📡 Wireless Networks Basics

- **Definition** → Networks using **radio frequency (RF)** instead of cables.
    
- **Adapters** → Convert data ↔ RF signals.
    
- **Ranges** →
    
    - Wi-Fi (LAN) → few hundred feet.
        
    - Cellular (WWAN: 3G/4G/5G) → city/regional coverage.
        
- **Bands** → 2.4 GHz & 5 GHz.
    
- **Access Point (WAP)** → Central device connecting wireless ↔ wired network.
    

## 🔑 Wi-Fi Connection (IEEE 802.11)

- Device sends **association request frame** to WAP.
    
- Frame includes:
    
    - MAC address
        
    - SSID (network name)
        
    - Supported data rates/channels
        
    - Security protocols (WPA2/WPA3)
        
- WAP grants access → device joins network.
    
- SSID can be hidden (not broadcasted) but still visible in authentication packets.
    

## 🛡️ Security Protocols

### WEP (Weak)

- Uses **RC4 cipher**.
    
- Keys: 40-bit (WEP-64) or 104-bit (WEP-104).
    
- Vulnerable due to **small IV (24-bit)** → brute force possible.
    
- CRC flaw allows plaintext recovery.
    

### WPA / WPA2 / WPA3 (Strong)

- WPA → Uses AES (128-bit).
    
- WPA-Personal → Pre-Shared Key (PSK).
    
- WPA-Enterprise → Centralized authentication (RADIUS/TACACS+).
    
- WPA3 → Strongest, modern standard.
    

## 🔑 Authentication Protocols

- **LEAP** → Cisco proprietary, uses shared key (weak).
    
- **PEAP** → Uses tunneled TLS, digital certificates (strong).
    
- **EAP-TLS** → Certificate-based, PKI, strong authentication.
    

## 🔐 TACACS+

- Used for authentication/authorization.
    
- Encrypts entire request packet (credentials, session info).
    
- Can use SSL/TLS or IPsec for encryption.
    

## ⚠️ Wireless Attack Example

- **Disassociation Attack** → Sends fake disassociation frames → disconnects clients.
    
- Purpose → Disrupt service or force reconnection (precursor to MITM).
    

## 🛡️ Wireless Hardening Techniques

1. **Disable SSID broadcasting** → Makes network harder to discover.
    
2. **Use WPA2/WPA3** → Strong encryption.
    
3. **MAC Filtering** → Allow only approved devices.
    
4. **Deploy EAP-TLS** → Strong certificate-based authentication.
    
5. **Built-in Firewalls** → Block malicious traffic.
    

## 🎯 Key Takeaway

- **WEP = obsolete, insecure.**
    
- **WPA2/WPA3 = must-have for modern networks.**
    
- **Authentication (PEAP, EAP-TLS)** adds strong protection.
    
- **Attacks (Disassociation, MITM)** exploit weak configs.
    
- **Hardening** → Disable SSID broadcast, enforce WPA2/3, MAC filtering, EAP-TLS.