## 🖧 Flat vs Segmented Networks

- **Flat Network (/24 subnet)** → All devices in same broadcast domain, easy to set up but weak security.
    
- **Segmented Networks (/25 or smaller)** → Divides devices into smaller groups, adds defense layers, harder for attackers to pivot silently.
    

**Analogy** →

- Flat network = house with only a door lock.
    
- Segmented network = house with fences, lights, bushes → multiple deterrents.
    

## 🛡️ Defense Examples

1. **Access Control Lists (ACLs)** → Like fences around property. Restrict which networks can talk.
    
    - Example: Printer network shouldn’t talk to servers via HTTP.
        
2. **Network Documentation** → Like lights around property. Visibility of all activity.
    
    - Example: Why is printer network talking to Internet?
        
3. **IDS/IPS (Suricata, Snort)** → Like bushes around windows. Deterrent to scans.
    
    - Example: Detect port scans from printer network.
        

## ⚠️ Pentester Oversight (Subnetting Mistake)

- **Common setup** → /24 subnet mask (255.255.255.0).
    
- **Issue** → Pentester used /24, but actual network was /25.
    
- **Result** → Could only see half the network, missed Domain Controller.
    
- **Lesson** → Always check subnet mask carefully.
    

**Example Network**

- Server Gateway → `10.20.0.1/25`
    
- Domain Controller → `10.20.0.10/25`
    
- Client Gateway → `10.20.0.129/25`
    
- Client Workstation → `10.20.0.200/25`
    
- Pentester → `10.20.0.252/24` (wrong mask).
    

## 🏠 Work From Home Setup (Diagram Concept)

- **Home Network** → Router connects smartphone, notebook, PC.
    
- **Company Network** → Router → Switch → Webserver, IP phone, printer, client hosts.
    
- **ISP** → Provides Internet + DNS resolution.
    
- **Flow** → Home user → ISP → DNS → Company webserver → Response back.
    

## 🌐 URL vs FQDN

- **FQDN** → `www.hackthebox.eu` → Address of building.
    
- **URL** → `https://www.hackthebox.eu/example?...` → Specifies floor, office, mailbox.
    

## 🔒 Extra Security Points

- **Web Server** → Should be in DMZ (separate network).
    
- **Workstations** → Isolated, host-based firewall to block workstation-to-workstation traffic.
    
- **Switch & Router** → On admin-only network (prevent OSPF spoofing).
    
- **IP Phones** → Separate network (low latency, prevent eavesdropping).
    
- **Printers** → Separate network (hard to secure, can leak credentials).
    

## 📖 Fun Story (Printer Exploit)

- Pentester shipped a malicious printer → Company plugged it in.
    
- Printer captured **Domain Admin credentials** via NTLMv2 authentication.
    
- **Lesson** → Printers should not:
    
    - Talk to Internet.
        
    - Communicate with workstations over port 445.
        
    - Initiate connections to workstations.
        

## 🖼️ Flow Diagram (Simplified)

Code

```
Home Network → Router → ISP → DNS → Company Router → Switch → Webserver
   | Smartphone, Notebook, PC
   | Company: Workstations, Printer, IP Phone
   | Segmentation: DMZ, Admin Net, Printer Net, Phone Net
```

## 🎯 Key Takeaway

- **Flat networks = weak security.**
    
- **Segmentation + ACLs + IDS/IPS = layered defense.**
    
- **Subnetting mistakes can blind assessments.**
    
- **Critical devices (web servers, printers, phones) must be isolated.**
    
- **Defense in depth slows attackers and protects high-value assets.**