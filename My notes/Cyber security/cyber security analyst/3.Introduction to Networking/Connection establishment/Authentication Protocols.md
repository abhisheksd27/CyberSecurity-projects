## 🔐 Authentication Protocols – Simplified Notes

### 1. **Kerberos**

- Ticket-based system using a **Key Distribution Center (KDC)**.
    
- Common in **domain environments** (Windows AD).
    
- Provides mutual authentication.
    

### 2. **SRP (Secure Remote Password)**

- Password-based protocol with cryptography.
    
- Protects against **eavesdropping** and **MITM attacks**.
    

### 3. **SSL / TLS**

- Cryptographic protocols for secure communication.
    
- **TLS** is the successor to SSL.
    
- Used in HTTPS, VPNs, email security.
    

### 4. **OAuth**

- Authorization protocol.
    
- Lets users grant **third-party access** without sharing passwords.
    
- Example: “Login with Google” on websites.
    

### 5. **OpenID**

- Decentralized authentication.
    
- Single identity across multiple sites.
    

### 6. **SAML**

- XML-based standard.
    
- Exchanges authentication/authorization data between parties.
    
- Common in enterprise **SSO** solutions.
    

### 7. **2FA / MFA**

- **2FA**: Two factors (password + phone).
    
- **MFA**: Multiple factors (password + token + biometrics).
    
- Stronger protection against credential theft.
    

### 8. **FIDO**

- Open standards for strong authentication.
    
- Supports biometrics, hardware tokens.
    

### 9. **PKI**

- Uses **public/private keys** + digital certificates.
    
- Foundation for SSL/TLS, digital signatures.
    

### 10. **SSO**

- Single login for multiple applications.
    
- Improves usability, reduces password fatigue.
    

### 11. **PAP / CHAP / EAP**

- **PAP**: Sends password in clear text (weak).
    
- **CHAP**: Three-way handshake, stronger than PAP.
    
- **EAP**: Framework supporting multiple methods (used in Wi-Fi, VPNs).
    

### 12. **SSH**

- Secure remote access protocol.
    
- Encrypts communication, supports authentication.
    
- Used for remote login, file transfer.
    

### 13. **HTTPS**

- Secure version of HTTP.
    
- Uses SSL/TLS for encryption + authentication.
    
- Standard for secure web browsing.
    

### 14. **LEAP / PEAP**

- **LEAP**: Cisco wireless protocol, uses RC4, vulnerable to dictionary attacks.
    
- **PEAP**: More secure, uses TLS + server-side certificates.
    
- Widely used in enterprise Wi-Fi authentication.
    

## 📊 Comparison Table

|Protocol|Type|Security Notes|
|---|---|---|
|Kerberos|Ticket-based|Strong in domain environments|
|SRP|Password-based|Resistant to MITM|
|SSL/TLS|Cryptographic|TLS is modern standard|
|OAuth|Authorization|Grants access without password sharing|
|OpenID|Authentication|Single identity across sites|
|SAML|Federation|XML-based, enterprise SSO|
|2FA/MFA|Multi-factor|Stronger identity verification|
|FIDO|Hardware/Biometrics|Open standard, strong auth|
|PKI|Key infrastructure|Basis for certificates|
|SSO|Credential reuse|Convenient, secure|
|PAP|Password|Weak, clear text|
|CHAP|Challenge-response|Stronger than PAP|
|EAP|Framework|Flexible, supports many methods|
|SSH|Secure remote|Encrypts + authenticates|
|HTTPS|Secure web|Encrypts traffic|
|LEAP|Wireless|Weak, outdated|
|PEAP|Wireless|Secure, TLS-based|

## 🔄 Flow Diagram – Authentication Process (Generic)

Code

```
User → Provides credentials
↓
Protocol → Validates credentials (password, token, certificate)
↓
Server → Issues session key / ticket
↓
Secure communication established
```

## 🌍 Real-World Examples

- **Kerberos** → Windows Active Directory logins.
    
- **OAuth** → “Login with Facebook/Google.”
    
- **TLS/HTTPS** → Secure online banking.
    
- **SSH** → Remote server administration.
    
- **PEAP** → Enterprise Wi-Fi authentication.
    
- **SAML + SSO** → Corporate apps with single login.