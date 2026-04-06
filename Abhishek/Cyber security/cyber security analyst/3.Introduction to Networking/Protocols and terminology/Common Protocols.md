## 📚 TCP vs UDP

- **TCP (Transmission Control Protocol)**
    
    - Connection-oriented (uses **Three-Way Handshake**).
        
    - Reliable, ensures delivery, but slower due to overhead.
        
    - Example: HTTP/HTTPS web browsing.
        
- **UDP (User Datagram Protocol)**
    
    - Connectionless, faster, less reliable.
        
    - Best for streaming/video/gaming where speed > reliability.
        
    - Example: YouTube video streaming.
        

## 🔑 Common TCP Protocols

|Protocol|Port|Description|
|---|---|---|
|Telnet|23|Remote login (insecure)|
|SSH|22|Secure remote login|
|HTTP|80|Web pages|
|HTTPS|443|Secure web pages|
|DNS|53|Domain name resolution|
|FTP|20-21|File transfer|
|SMTP|25|Email sending|
|POP3|110|Email retrieval|
|IMAP|143|Email access|
|SMB|445|File sharing (Windows)|
|NFS|111, 2049|File sharing (Unix/Linux)|
|DHCP|67, 68|Dynamic IP assignment|
|RDP|3389|Remote desktop|
|LDAP|389|Directory services|
|Kerberos|88|Authentication|
|OSPF|89|Routing protocol|
|PPTP|1723|VPN tunneling|
|SQL Server|1433|Database connections|
|Oracle TNS|1521|Oracle DB listener|

## 🔑 Common UDP Protocols

|Protocol|Port|Description|
|---|---|---|
|DNS|53|Domain resolution|
|TFTP|69|Simple file transfer|
|NTP|123|Time synchronization|
|SNMP|161|Device management|
|RIP|520|Routing info exchange|
|DHCP|67|Dynamic IP assignment|
|NetBIOS|137|Windows name resolution|
|Syslog|514|Log collection|
|VNC|5900|Remote desktop sharing|
|PostgreSQL|5432|Database connections|
|UPnP|1900|Device discovery|

## 🛡️ ICMP (Internet Control Message Protocol)

- Used for **error reporting & diagnostics**.
    
- **Requests**: Echo (ping), Timestamp, Address Mask.
    
- **Messages**: Echo reply, Destination unreachable, Redirect, Time exceeded.
    
- **TTL (Time-To-Live)** → Prevents infinite loops, decremented at each hop.
    
- **OS Fingerprinting** → Default TTL values differ:
    
    - Windows → 128
        
    - Linux/macOS → 64
        
    - Solaris → 255
        

## 📞 VoIP (Voice over IP)

- Uses **SIP (Session Initiation Protocol)** → Ports 5060/5061.
    
- Alternative: H.323 (Port 1720).
    
- SIP Methods:
    
    - **INVITE** → Start session.
        
    - **ACK** → Confirm invite.
        
    - **BYE** → End session.
        
    - **REGISTER** → Register user agent.
        
    - **OPTIONS** → Query server capabilities.
        
- Vulnerability: SIP can be used for **user enumeration** (e.g., via OPTIONS requests).
    

## 🎯 Key Takeaway

- **TCP = reliable, connection-oriented.**
    
- **UDP = fast, connectionless.**
    
- **ICMP = diagnostics & error reporting.**
    
- **VoIP (SIP)** = real-time communication, but can leak info if misconfigured.
    
- Knowing **ports + protocols** is essential for penetration testing and network defense.