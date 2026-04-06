## 🔐 Encryption Basics

- **Purpose**: Protect data (payments, emails, personal info) from unauthorized access or manipulation.
    
- **Process**: Data transformed into unreadable ciphertext using mathematical algorithms.
    
- **Types**:
    
    - **Symmetric Encryption** → same key for encryption & decryption.
        
    - **Asymmetric Encryption** → public key for encryption, private key for decryption.
        

## 🔑 Symmetric Encryption

- **Same key** used by sender & receiver.
    
- **Challenge**: Secure key distribution.
    
- **Examples**:
    
    - **DES** → 56-bit key, outdated.
        
    - **3DES** → triple encryption, stronger but slower.
        
    - **AES** → modern standard, 128/192/256-bit keys, fast & secure.
        

**Use cases**: Encrypting large amounts of data (files, network traffic).

## 🔑 Asymmetric Encryption

- **Two keys**: Public (encrypt) & Private (decrypt).
    
- **Advantages**:
    
    - No need for secret key exchange.
        
    - Enables **digital signatures** for authentication.
        
- **Examples**:
    
    - **RSA** → prime factorization.
        
    - **PGP** → secure emails.
        
    - **ECC** → efficient, strong security.
        

**Use cases**: SSL/TLS, VPNs, SSH, PKI, cloud security.

## 📊 Comparison Table

|Feature|Symmetric|Asymmetric|
|---|---|---|
|Keys|Same key|Public & private key|
|Speed|Fast|Slower|
|Security|Depends on key secrecy|Strong, based on math problems|
|Use cases|Bulk data encryption|Secure communication, authentication|

## 🔄 Cipher Modes (Block Cipher Operations)

|Mode|Description|Use Cases|
|---|---|---|
|**ECB**|Encrypts blocks independently; insecure (patterns visible).|Rarely used|
|**CBC**|Chains blocks; hides patterns.|Disk encryption, TLS|
|**CFB**|Stream-like encryption.|Real-time data, BitLocker|
|**OFB**|Stream mode, better keystream.|SSH, PKCS|
|**CTR**|Counter-based, parallelizable.|IPsec, BitLocker|
|**GCM**|Adds integrity protection.|VPNs, wireless comms|

## 📦 Visual Flow – Encryption Process

Code

```
Plaintext → Encryption Algorithm + Key → Ciphertext
Ciphertext → Decryption Algorithm + Key → Plaintext
```

- **Symmetric**: Same key used both ways.
    
- **Asymmetric**: Public key encrypts, private key decrypts.
    

## 🌍 Real-World Examples

- **AES** → Wi-Fi security (WPA2/WPA3), IPsec VPNs, VoIP.
    
- **RSA/ECC** → SSL/TLS certificates for HTTPS.
    
- **PGP** → Secure email communication.
    
- **GCM mode** → VPN tunnels, wireless security.
    

This gives you a **layered view**:

- **Symmetric** → fast, bulk encryption.
    
- **Asymmetric** → secure communication & authentication.
    
- **Cipher modes** → define how block ciphers handle data streams.