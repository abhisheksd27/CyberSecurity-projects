## 📚 MAC vs IP Address

- **MAC Address** → Unique hardware identifier (like _apartment number_).
    
- **IP Address (IPv4/IPv6)** → Logical address for delivery across networks (like _postal address_).
    
- **Analogy** →
    
    - IP = Building + District.
        
    - MAC = Exact floor + apartment.
        

## 🌍 IPv4 Structure

- **Format** → 32-bit binary → 4 octets (0–255 each).
    
- **Notation** → Dotted-decimal (e.g., `192.168.10.39`).
    
- **Total Addresses** → ~4.29 billion unique addresses.
    
- **Division** → Network part + Host part.
    

## 🏷️ IPv4 Classes (Historical)

|Class|Range (First Octet)|Subnet Mask|CIDR|Hosts per Network|
|---|---|---|---|---|
|A|1–127|255.0.0.0|/8|~16 million|
|B|128–191|255.255.0.0|/16|~65k|
|C|192–223|255.255.255.0|/24|254|
|D|224–239|Multicast|—|Multicast only|
|E|240–255|Reserved|—|Experimental|

## 📡 Subnetting

- **Subnet Mask** → Defines which bits = network vs host.
    
- Example: `255.255.255.0` → `/24` → 24 bits for network, 8 bits for host.
    
- **Reserved Addresses** →
    
    - **Network Address** → Identifies subnet (first IP).
        
    - **Broadcast Address** → Last IP, sends to all devices in subnet.
        
- **Default Gateway** → Router IP (often first/last usable address).
    

## 🔢 Binary Conversion Example

IPv4 Address: `192.168.10.39`

- Binary: `11000000.10101000.00001010.00100111`
    
- Decimal: `192.168.10.39`
    

Subnet Mask: `255.255.255.0`

- Binary: `11111111.11111111.11111111.00000000`
    
- CIDR: `/24`
    

## 🖼️ Flow Diagram (Addressing)

Code

```
MAC Address → Identifies device within local network
IP Address → Identifies device across networks
Subnet Mask → Defines network vs host portion
Gateway → Connects subnet to other networks
Broadcast → Sends to all devices in subnet
```

## 🎯 Key Takeaway

- **MAC = Hardware identity**, **IP = Logical identity**.
    
- **IPv4 = 32-bit, 4 octets, ~4.29B addresses**.
    
- **Classes (A–E)** → Historical, replaced by **CIDR**.
    
- **Subnetting** → Divides networks into smaller segments.
    
- **CIDR** → Flexible notation (`/24`, `/16`, etc.), replaces rigid classes.