## 📚 DNS Basics

- **Definition** → Phonebook of the Internet.
    
- **Purpose** → Translates human-friendly domain names → machine-readable IP addresses.
    
- **Without DNS** → We’d need to memorize IPs like `93.184.216.34`.
    
- **With DNS** → Just type `www.example.com`.
    

## 🧩 Domain Names vs IP Addresses

- **Domain Name** → Readable (e.g., `www.google.com`).
    
- **IP Address** → Numerical (e.g., `142.251.46.174`).
    
- **DNS Role** → Bridges domain ↔ IP.
    

## 🌳 DNS Hierarchy

1. **Root Servers** → Top of DNS tree.
    
2. **Top-Level Domains (TLDs)** → `.com`, `.org`, `.net`, `.uk`, `.de`.
    
3. **Second-Level Domains** → `example` in `example.com`.
    
4. **Subdomains/Hostnames** → `www` in `www.example.com`, `accounts` in `accounts.google.com`.
    

## ⚙️ DNS Resolution (Steps)

1. User types `www.example.com`.
    
2. Computer checks **local DNS cache**.
    
3. If not found → Queries **recursive DNS server** (ISP or Google DNS).
    
4. Recursive server → Contacts **Root Server**.
    
5. Root → Points to **TLD server** (e.g., `.com`).
    
6. TLD → Directs to **Authoritative server** for `example.com`.
    
7. Authoritative server → Returns IP (`93.184.216.34`).
    
8. Recursive server → Sends IP back to user’s computer.
    
9. Browser connects to website using IP.
    

## 🖼️ Flow Diagram (DNS Query)

Code

```
PC → Recursive DNS → Root Server → TLD Server → Authoritative Server → IP Address → PC connects to website
```

## 🎯 Key Takeaway

- **DNS = Internet’s phonebook.**
    
- **Hierarchy** → Root → TLD → Second-level → Subdomain.
    
- **Resolution** → Domain → IP in milliseconds.
    
- Makes Internet **human-friendly + efficient**.