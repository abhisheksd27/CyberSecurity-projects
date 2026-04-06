## 🌐 TCP vs UDP

### TCP (Transmission Control Protocol)

- **Connection-oriented** → like a phone call.
    
- **Reliable** → ensures all data arrives; retransmits if errors occur.
    
- **Slower** → extra overhead for error checking and acknowledgments.
    
- **Use cases**: Web pages, emails, file transfers.
    

### UDP (User Datagram Protocol)

- **Connectionless** → like sending postcards.
    
- **Fast** → no error recovery or acknowledgment.
    
- **Unreliable** → some packets may be lost.
    
- **Use cases**: Streaming video, online gaming, VoIP.
    

## 📦 IP Packet Structure

Think of an **IP packet** as a **letter in an envelope**:

- **Envelope (Header)** → sender, recipient, routing instructions.
    
- **Letter (Payload)** → actual data (TCP segment, UDP datagram, etc.).
    

### IP Header Fields (simplified)

- **Version** → IPv4 or IPv6.
    
- **Header Length** → size of header.
    
- **Class of Service** → priority.
    
- **Total Length** → packet size.
    
- **Identification / Flags / Fragment Offset** → fragmentation info.
    
- **TTL (Time to Live)** → how long packet stays on network.
    
- **Protocol** → TCP, UDP, ICMP, etc.
    
- **Checksum** → error detection.
    
- **Source/Destination** → sender & receiver IPs.
    
- **Options/Padding** → extra info.
    

## 🔍 Network Sniffing Example

TCPdump output shows **IP IDs** incrementing continuously across two IP addresses → indicates they belong to the same host.

Code

```
IP 10.129.1.100 > 10.129.1.1: id 1337
IP 10.129.1.100 > 10.129.1.1: id 1338
IP 10.129.2.200 > 10.129.1.1: id 1340
```

## 🛣️ Record-Route & Traceroute

- **Record-Route field** → logs all devices a packet passes through.
    
- **Traceroute process**:
    
    1. Send TCP SYN with TTL=1.
        
    2. Router decrements TTL → sends ICMP Time Exceeded.
        
    3. Increase TTL step by step.
        
    4. Continue until packet reaches destination → SYN/ACK or RST received.
        

This maps the full path to the destination.

## 📑 TCP Segment Structure

- **Source/Destination Port** → sender & receiver apps.
    
- **Sequence Number** → order of data.
    
- **Acknowledgment Number** → confirms receipt.
    
- **Flags** → SYN, ACK, FIN, etc.
    
- **Window Size** → how much data receiver can accept.
    
- **Checksum** → error detection.
    
- **Urgent Pointer** → marks urgent data.
    
- **Payload** → actual transmitted data.
    

## 📑 UDP Datagram Structure

- **Source/Destination Port** → sender & receiver apps.
    
- **Length** → size of datagram.
    
- **Checksum** → error detection.
    
- **Payload** → transmitted data.
    

No sequence numbers, no acknowledgments → faster but less reliable.

## ⚠️ Blind Spoofing Attack

- Attacker forges IP header fields (source/destination, ports, ISN).
    
- Target host may establish a connection with attacker’s spoofed info.
    
- Used to disrupt connections, intercept traffic, or impersonate hosts.
    

## 🔄 Flow Diagram – TCP vs UDP

Code

```
TCP: Sender → SYN → Receiver
     Receiver → SYN/ACK → Sender
     Sender → ACK → Connection established
     Reliable data transfer with acknowledgments

UDP: Sender → Datagram → Receiver
     No handshake, no acknowledgment
     Fast but may lose packets
```

## 🌍 Real-World Examples

- **TCP** → Email (SMTP), Web browsing (HTTP/HTTPS), File transfer (FTP).
    
- **UDP** → Online gaming, video streaming, DNS queries.
    
- **Traceroute** → Network troubleshooting.
    
- **Blind Spoofing** → Attack scenario in penetration testing.