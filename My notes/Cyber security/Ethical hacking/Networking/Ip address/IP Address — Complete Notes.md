### **1. What is an IP Address?**

- **IP = Internet Protocol**
- A **unique numerical label** assigned to every device on a network
- Used for **identification** (who you are) and **location addressing** (where you are)
- Works like a **postal address** for your device on the internet

---

### **2. Versions of IP**

#### **IPv4**

- Format: `192.168.64.6`
- **32-bit** address
- Written in **4 octets** separated by dots
- Each octet = **0 to 255**
- Total addresses: **~4.3 billion**
- Currently **exhausted** — not enough for all devices

#### **IPv6**

- Format: `fe80::6488:ebff:fe53:9efc`
- **128-bit** address
- Written in **8 groups of hexadecimal**
- Total addresses: **340 undecillion** (virtually unlimited)
- Created to **replace IPv4**

|Feature|IPv4|IPv6|
|---|---|---|
|Bits|32|128|
|Format|Decimal|Hexadecimal|
|Example|192.168.1.1|fe80::1|
|Addresses|~4.3 billion|~340 undecillion|
|Security|Optional|Built-in (IPSec)|

---

### **3. Types of IP Addresses**

#### **A. Public IP**

- Assigned by your **ISP (Internet Service Provider)**
- **Visible on the internet**
- Unique across the **entire internet**
- Example: `103.21.244.5`
- Used when you access websites, stream, etc.

#### **B. Private IP**

- Used **within local networks** (home/office)
- **Not visible** on the internet
- Assigned by your **router**
- Private IP ranges:

|Class|Range|Usage|
|---|---|---|
|A|10.0.0.0 – 10.255.255.255|Large networks|
|B|172.16.0.0 – 172.31.255.255|Medium networks|
|C|192.168.0.0 – 192.168.255.255|Home/small office|

#### **C. Loopback IP**

- Always `127.0.0.1`
- Refers to **your own machine**
- Used for **testing and local services**
- Never leaves the device

#### **D. Static IP**

- **Manually assigned** — never changes
- Used for **servers, printers, cameras**
- More reliable but costs more

#### **E. Dynamic IP**

- **Automatically assigned** by DHCP server
- **Changes periodically**
- Used by most home devices
- Cost-effective

#### **F. Link-Local IP**

- Range: `169.254.0.0/16` (IPv4), `fe80::/10` (IPv6)
- Assigned **automatically** when no DHCP is available
- Only works on the **local network segment**
- Cannot be routed to internet

---

### **4. IP Address Structure (IPv4)**

```
192  .  168  .  64  .  6
 ↑       ↑       ↑      ↑
Oct1    Oct2   Oct3   Oct4

|----Network Part----|--Host--|
```

- **Network part** → identifies the network
- **Host part** → identifies the specific device

---

### **5. Subnetting & Netmask**

- **Subnet Mask** divides IP into Network + Host
- Example: `255.255.255.0`
    - `255` = **network portion** (fixed)
    - `0` = **host portion** (variable)
- Written in CIDR notation: `/24` means 24 bits for network

|Subnet Mask|CIDR|Hosts Available|
|---|---|---|
|255.0.0.0|/8|16 million|
|255.255.0.0|/16|65,534|
|255.255.255.0|/24|254|
|255.255.255.128|/25|126|

---

### **6. Special IP Addresses**

|Address|Purpose|
|---|---|
|`127.0.0.1`|Loopback / Localhost|
|`0.0.0.0`|All interfaces / default route|
|`255.255.255.255`|Limited broadcast|
|`192.168.x.x`|Private home network|
|`169.254.x.x`|Link-local (no DHCP)|
|`8.8.8.8`|Google's public DNS|
|`1.1.1.1`|Cloudflare's public DNS|

---

### **7. How IP Works — Step by Step**

```
You type google.com
        ↓
DNS resolves it to 142.250.182.46 (Public IP)
        ↓
Your router sends request from your Private IP
        ↓
NAT converts Private IP → Public IP
        ↓
Packet travels through internet routers
        ↓
Google receives it and responds back
        ↓
Response returns to your Public IP
        ↓
NAT converts back → Your Private IP
        ↓
You see Google's homepage
```

---

### **8. NAT (Network Address Translation)**

- Allows **multiple devices** to share **one public IP**
- Your router acts as a **translator**
- Private IPs are **hidden behind** the public IP
- Why it exists → **IPv4 address exhaustion**

---

### **9. DHCP (Dynamic Host Configuration Protocol)**

- Automatically **assigns IP addresses** to devices
- Your router runs a **DHCP server**
- When you connect → router gives you an IP, subnet mask, gateway, DNS
- Lease time → IP is **temporary**, renewed periodically

---

### **10. IP in Cybersecurity Context**

|Concept|Significance|
|---|---|
|IP Spoofing|Faking source IP to **hide identity**|
|IP Scanning|Finding **active hosts** on network (nmap)|
|IP Blocking|Firewalls **deny traffic** from specific IPs|
|Geolocation|Approximate **physical location** from IP|
|VPN|**Masks real IP** with VPN server's IP|
|Tor|Routes through **multiple IPs** for anonymity|

---

> **Key Takeaway:** IP addresses are the **foundation of all network communication** — every packet sent or received is routed using IP addresses, making them the most fundamental concept in networking.