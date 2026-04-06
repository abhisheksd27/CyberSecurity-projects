## 🌐 Step-by-Step Process

### 1. **Accessing WLAN**

- Laptop identifies correct SSID (Wi-Fi name).
    
- User authenticates (WPA2/WPA3 password).
    
- Connection established → DHCP begins IP configuration.
    

### 2. **DHCP (Local IP Assignment)**

- Laptop requests IP from router’s DHCP server.
    
- DHCP server assigns **private IP** (e.g., `192.168.1.10`) + subnet mask, gateway, DNS.
    
- Laptop now has valid local network configuration.
    

### 3. **DNS Resolution**

- Browser needs IP of `www.example.com`.
    
- Laptop sends DNS query → DNS server (ISP/Google DNS).
    
- DNS server responds with IP (e.g., `93.184.216.34`).
    

### 4. **Data Encapsulation (OSI/TCP-IP Layers)**

- **Application Layer** → Browser creates HTTP/HTTPS request.
    
- **Transport Layer** → TCP segment (port 80/443).
    
- **Internet Layer** → IP packet (src: `192.168.1.10`, dest: `93.184.216.34`).
    
- **Link Layer** → Ethernet/Wi-Fi frame with MAC addresses.
    
- ARP used to find router’s MAC → Frame sent to router.
    

### 5. **NAT (Network Address Translation)**

- Router replaces private IP (`192.168.1.10`) → public IP (`203.0.113.45`).
    
- Packet forwarded to ISP → Internet → Destination server.
    
- Intermediate routers forward based on destination IP.
    

### 6. **Server Processing**

- Server firewall checks traffic (port 80/443).
    
- Web server (Apache/Nginx/IIS) processes request.
    
- Prepares webpage (HTML, CSS, JS, images).
    
- Sends response back → Source = server IP (`93.184.216.34`), Destination = router public IP (`203.0.113.45`).
    

### 7. **Response & Decapsulation**

- Router NAT maps public IP back → laptop’s private IP (`192.168.1.10`).
    
- Laptop receives packet → Strips headers (Ethernet → IP → TCP).
    
- Browser reads application data (HTML/CSS/JS).
    
- Webpage displayed to user.
    

## 🖼️ Flow Diagram (Website Access)

Code

```
Laptop → WLAN (SSID + WPA2/WPA3)
       → DHCP assigns private IP (192.168.1.10)
       → DNS query → DNS server → IP (93.184.216.34)
       → HTTP request encapsulated (TCP/IP layers)
       → Router NAT (203.0.113.45 public IP)
       → Internet → Destination server
       → Server processes & responds
       → Router NAT maps back → Laptop
       → Browser decapsulates → Displays webpage
```

## 🎯 Key Takeaway

- **DHCP** → Assigns local IP.
    
- **DNS** → Resolves domain → IP.
    
- **Encapsulation** → Wraps data through OSI/TCP-IP layers.
    
- **NAT** → Translates private ↔ public IP.
    
- **Server** → Processes request, sends response.
    
- **Decapsulation** → Browser extracts data → Shows webpage.