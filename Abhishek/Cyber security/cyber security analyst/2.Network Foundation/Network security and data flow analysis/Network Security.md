## 🔑 CIA Triad (Core Principles)

1. **Confidentiality** → Only authorized users can access data.
    
2. **Integrity** → Data remains accurate and unaltered.
    
3. **Availability** → Resources accessible when needed.
    

## 🔥 Firewalls

- **Definition** → Security device/software that filters traffic based on rules.
    
- **Analogy** → Security guard checking who can enter/exit.
    
- **Placement** → Between Internet ↔ Internal Network.
    

**Types of Firewalls**

1. **Packet Filtering** → Layer 3 & 4, checks IP, port, protocol.
    
    - Example: Allow HTTP (80), HTTPS (443), block others.
        
2. **Stateful Inspection** → Tracks connection states, allows only valid sessions.
    
    - Example: Inbound reply allowed only if outbound request exists.
        
3. **Application Layer (Proxy)** → Layer 7, inspects content.
    
    - Example: Web proxy filtering malicious HTTP requests.
        
4. **Next-Gen Firewall (NGFW)** → Combines stateful + deep inspection + IDS/IPS.
    
    - Example: Blocks malicious IPs, inspects encrypted traffic.
        

**Diagram Flow**

Code

```
Internet → Firewall → Router/Modem → Internal Devices (PC, Laptop, Smartphone)
```

## 🛡️ IDS/IPS

- **IDS (Intrusion Detection System)** → Detects suspicious activity, alerts only.
    
- **IPS (Intrusion Prevention System)** → Detects + blocks malicious traffic in real time.
    
- **Key Difference** → IDS = Detect, IPS = Detect + Prevent.
    

**Detection Techniques**

- **Signature-based** → Matches known attack patterns.
    
- **Anomaly-based** → Flags unusual behavior vs normal traffic.
    

**Types of IDS/IPS**

1. **Network-Based (NIDS/NIPS)** → Monitors traffic at network points.
    
    - Example: Sensor at core switch in data center.
        
2. **Host-Based (HIDS/HIPS)** → Runs on individual devices.
    
    - Example: Antivirus/endpoint agent on server.
        

**Placement Options**

- Behind firewall → Inspect remaining traffic.
    
- In DMZ → Monitor public-facing servers.
    
- On endpoints → Detect host-level threats.
    

**Diagram Flow**

Code

```
Internet → Firewall → IDS/IPS → Router/Modem → Internal Devices
```

## 🧩 Best Practices

1. **Define Clear Policies** → Least privilege rules.
    
2. **Regular Updates** → Firewall, IDS/IPS signatures, OS patches.
    
3. **Monitor & Log Events** → Review logs for suspicious activity.
    
4. **Layered Security (Defense in Depth)** → Firewalls + IDS/IPS + antivirus + endpoint protection.
    
5. **Periodic Penetration Testing** → Simulate attacks to test defenses.
    

## 🎯 Key Takeaway

- **CIA Triad** → Foundation of security.
    
- **Firewalls** → First line of defense, filter traffic.
    
- **IDS/IPS** → Detect & prevent deeper threats.
    
- **Best Practices** → Policies, updates, monitoring, layered defense.