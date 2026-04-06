## 📚 IPv6 Basics

- **Successor to IPv4** → 128-bit addresses (vs 32-bit in IPv4).
    
- **Representation** → Hexadecimal, divided into 8 blocks of 16 bits (4 hex digits each).
    
- **Notation** → `fe80::dd80:b1a9:6687:2d3b/64` (shortened form).
    
- **Dual Stack** → IPv4 + IPv6 can run simultaneously.
    
- **No NAT needed** → End-to-end principle, every device can have a public IP.
    

## 🔑 Advantages of IPv6

- Larger address space (~340 undecillion addresses).
    
- Self-configuration (SLAAC).
    
- Multiple addresses per interface.
    
- Faster routing.
    
- Mandatory IPsec (security).
    
- Supports very large data packets (up to 4 GB).
    

## 🏷️ IPv4 vs IPv6

|Feature|IPv4|IPv6|
|---|---|---|
|Bit length|32-bit|128-bit|
|Address range|~4.3 billion|~340 undecillion|
|Representation|Decimal (dotted)|Hexadecimal (colon-separated)|
|Prefix notation|10.10.10.0/24|fe80::dd80:b1a9:6687:2d3b/64|
|Dynamic addressing|DHCP|SLAAC / DHCPv6|
|IPsec|Optional|Mandatory|
|Broadcast|Supported|Eliminated (uses multicast)|

## 📡 IPv6 Address Types

1. **Unicast** → One-to-one communication.
    
2. **Anycast** → One-to-nearest communication (multiple interfaces, only one responds).
    
3. **Multicast** → One-to-many communication (all assigned interfaces receive).
    
    - Note: IPv6 **eliminates broadcast** → replaced by multicast.
        

## 🔢 Hexadecimal System Refresher

- Decimal → 0–9
    
- Binary → 0/1
    
- Hexadecimal → 0–F (16 states).
    

**Example Conversion (IPv4 → Hex):**

- IPv4: `192.168.12.160`
    
- Binary: `11000000.10101000.00001100.10100000`
    
- Hex: `C0.A8.0C.A0`
    

## 🖼️ IPv6 Address Structure

- **Network Prefix** → Identifies network/subnet.
    
- **Interface Identifier (Suffix)** → Host part, often derived from MAC → expanded to 64 bits.
    
- **Default Prefix Length** → `/64` (but can be `/32`, `/48`, `/56`).
    

## 📝 RFC 5952 Notation Rules

- Use lowercase letters.
    
- Omit leading zeros in each block.
    
- Replace consecutive blocks of zeros with `::` (only once).
    

**Example:**

- Full → `fe80:0000:0000:0000:dd80:b1a9:6687:2d3b/64`
    
- Short → `fe80::dd80:b1a9:6687:2d3b/64`
    

## 🎯 Key Takeaway

- **IPv6 = Future of Internet addressing.**
    
- Vast address space, built-in security, no NAT.
    
- Uses **hexadecimal + prefix notation**.
    
- **Unicast, Anycast, Multicast** replace IPv4’s broadcast.
    
- Shortened notation makes long addresses manageable.