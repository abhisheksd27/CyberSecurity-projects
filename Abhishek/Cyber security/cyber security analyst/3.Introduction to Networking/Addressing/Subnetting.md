## 🧩 Example Setup

- **IP Address** → `192.168.12.160`
    
- **Subnet Mask** → `255.255.255.192`
    
- **CIDR** → `/26`
    

## 1️⃣ Identify Network & Host Bits

- `/26` → 26 bits reserved for **network**, 6 bits left for **hosts**.
    
- **Total addresses** = 26=64.
    
- Usable hosts = 64−2=62 (subtract network + broadcast).
    

## 2️⃣ Find Network Address

- Subnet mask `/26` = `255.255.255.192`.
    
- Block size = 256−192=64.
    
- Starting subnet ranges: `192.168.12.0`, `192.168.12.64`, `192.168.12.128`, `192.168.12.192`.
    
- Given IP `192.168.12.160` falls in **192.168.12.128/26**.
    
- **Network Address** = `192.168.12.128`.
    

## 3️⃣ Find Broadcast Address

- Add block size (64) → `192.168.12.128 + 64 = 192.168.12.192`.
    
- Broadcast = one less → `192.168.12.191`.
    

## 4️⃣ Find Host Range

- First usable host = `192.168.12.129`.
    
- Last usable host = `192.168.12.190`.
    
- Total usable = 62 hosts.
    

## ✅ Summary Table

|Item|Value|
|---|---|
|Network Address|192.168.12.128|
|First Host|192.168.12.129|
|Last Host|192.168.12.190|
|Broadcast Address|192.168.12.191|
|Usable Hosts|62|

## 5️⃣ Subnetting into 4 Smaller Networks

- Requirement → Divide `/26` into 4 subnets.
    
- Each subnet = 64÷4=16 addresses.
    
- New mask = `/28` (255.255.255.240).
    

**Subnets:**

1. `192.168.12.128/28` → Hosts: 192.168.12.129–142, Broadcast: 143
    
2. `192.168.12.144/28` → Hosts: 145–158, Broadcast: 159
    
3. `192.168.12.160/28` → Hosts: 161–174, Broadcast: 175
    
4. `192.168.12.176/28` → Hosts: 177–190, Broadcast: 191
    

## 🧠 Mental Subnetting Trick

- Remember **block sizes**:
    
    - /24 → 256
        
    - /25 → 128
        
    - /26 → 64
        
    - /27 → 32
        
    - /28 → 16
        
    - /29 → 8
        
    - /30 → 4
        
    - /31 → 2
        
- Just subtract subnet mask from 256 to get block size.
    
- Then add block size to find next subnet range.
    

## 🎯 Key Takeaway

- **Subnetting = divide address space into smaller logical networks.**
    
- Always calculate: **Network Address → Broadcast → Host Range → Usable Hosts.**
    
- Use **block size trick (256 - mask)** for quick mental math.