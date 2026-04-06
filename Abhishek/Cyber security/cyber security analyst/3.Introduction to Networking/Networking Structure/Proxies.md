## 📚 What is a Proxy?

- **Definition** → A mediator device/service that sits in the middle of a connection.
    
- **Key Point** → Must be able to **inspect traffic contents**.
    
- **OSI Layer** → Usually operates at **Layer 7 (Application Layer)**.
    
- **Misconception** → VPN ≠ Proxy (VPN changes IP/location but doesn’t inspect traffic).
    

## 🔑 Types of Proxies

### 1. **Forward Proxy (Dedicated Proxy)**

- **Definition** → Client → Proxy → Internet.
    
- **Use Cases** →
    
    - Corporate networks (filtering, malware defense).
        
    - Tools like **Burp Suite** (HTTP request forwarding).
        
- **Example** → Sensitive PCs must go through proxy to access Internet.
    

### 2. **Reverse Proxy**

- **Definition** → Internet → Proxy → Internal Server.
    
- **Use Cases** →
    
    - Protect servers from direct exposure.
        
    - Load balancing, DDOS protection (e.g., **Cloudflare**).
        
    - Web Application Firewalls (WAFs) like **ModSecurity**.
        
- **Pentesting Use** → Reverse proxy on infected endpoint to bypass firewalls.
    

### 3. **Transparent vs Non-Transparent Proxy**

- **Transparent Proxy** → Client doesn’t know it exists. Intercepts traffic silently.
    
- **Non-Transparent Proxy** → Requires explicit configuration in client software.
    
- **Example** →
    
    - Transparent → ISP intercepting traffic.
        
    - Non-Transparent → Browser configured with proxy settings.
        

## 🖼️ Flow Diagram (Simplified)

Code

```
Forward Proxy:
Client → Proxy → Internet → Webserver

Reverse Proxy:
Internet → Firewall → Reverse Proxy → Internal Webserver

Transparent Proxy:
Client → (Intercepted silently) → Internet

Non-Transparent Proxy:
Client (configured) → Proxy → Internet
```

## 🎯 Key Takeaway

- **Forward Proxy** → Protects clients, filters outgoing requests.
    
- **Reverse Proxy** → Protects servers, filters incoming requests.
    
- **Transparent Proxy** → Invisible to client.
    
- **Non-Transparent Proxy** → Explicitly configured.
    
- **Proxies ≠ VPNs** → VPNs change location/IP, proxies inspect traffic.