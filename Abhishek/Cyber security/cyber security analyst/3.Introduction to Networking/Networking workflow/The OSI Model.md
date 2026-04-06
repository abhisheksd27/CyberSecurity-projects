## 📚 OSI Model Overview

- **Goal** → Standard reference model for communication across different systems.
    
- **Structure** → 7 hierarchical layers, each with defined tasks.
    
- **Process** → Sender moves data **top (Layer 7) → bottom (Layer 1)**; Receiver reverses **bottom → top**.
    
- **Orientation** →
    
    - Layers 1–2 → Physical/medium.
        
    - Layers 3–4 → Transport-oriented.
        
    - Layers 5–7 → Application-oriented.
        

## 🔑 OSI Layers (Top → Bottom)

1. **Application (Layer 7)**
    
    - Provides application functions (HTTP, FTP, SMTP).
        
    - Controls input/output of data.
        
2. **Presentation (Layer 6)**
    
    - Translates data formats (encryption, compression).
        
    - Makes data independent of system differences.
        
3. **Session (Layer 5)**
    
    - Manages logical connections (sessions).
        
    - Prevents breakdowns, maintains communication.
        
4. **Transport (Layer 4)**
    
    - End-to-end delivery, segmentation, error detection.
        
    - Protocols: TCP, UDP.
        
5. **Network (Layer 3)**
    
    - Logical addressing & routing.
        
    - Packet forwarding across networks.
        
    - Protocol: IP.
        
6. **Data Link (Layer 2)**
    
    - Reliable transmission over medium.
        
    - Frames, MAC addressing, error detection.
        
7. **Physical (Layer 1)**
    
    - Actual transmission: electrical, optical, radio signals.
        
    - Cables, fiber, wireless.
        

## 🖼️ Flow Diagram (Communication Path)

Code

```
Sender: Application → Presentation → Session → Transport → Network → Data-Link → Physical
Receiver: Physical → Data-Link → Network → Transport → Session → Presentation → Application
```

## ⚙️ Encapsulation & Decapsulation

- **Encapsulation** → Each layer adds its own header to the data (PDU).
    
- **Decapsulation** → Receiver strips headers layer by layer until data is usable.
    
- **Result** → Secure, reliable, structured communication.
    

## 🎯 Key Takeaway

- **OSI = Reference model** → 7 layers, strict separation of tasks.
    
- **Sender & Receiver both run through all 7 layers.**
    
- **Encapsulation/Decapsulation** ensures compatibility, reliability, and performance.