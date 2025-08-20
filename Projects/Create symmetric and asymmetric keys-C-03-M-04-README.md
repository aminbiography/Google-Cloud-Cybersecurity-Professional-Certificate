# Create Symmetric and Asymmetric Keys  

---

## Project Objective  
- To **create and manage symmetric and asymmetric keys** in Google Cloud KMS.  
- To **understand the differences** between symmetric and asymmetric cryptography.  
- To **apply key management techniques** for secure data storage and transmission.  
- To **gain practical experience** in encryption, decryption, and digital signatures.  

---

## Activity Overview  
- **Symmetric keys**: Use the same key for encryption and decryption → fast and efficient.  
- **Asymmetric keys**: Use a public/private key pair → secure but slower.  
- **Real-world application**: HTTPS uses asymmetric keys for the handshake, then switches to symmetric keys for faster bulk data encryption.  

---

## Scenario  
- Organization: **Cymbal Bank**  
- Data: Financial transactions and sensitive PII (Personally Identifiable Information).  
- Challenge: Protect data **at rest, in transit, and in use** during migration from on-premises to cloud.  
- Solution: Use **Google Cloud KMS** to generate both symmetric and asymmetric keys.  

---

## Setup  
- **Google Cloud KMS** (Key Management Service)  
- **Key Ring:** `demo-key-ring`  
- **Protection level:** Software  
- **Key rotation policy:** 90 days (for symmetric key)  

---

## Task 1: Create a Symmetric Key  
Steps performed:  
1. Created a key ring → `demo-key-ring`.  
2. Created a symmetric key → `demo-key`.  
3. Chose **region-specific** location.  
4. Protection level: **Software**.  
5. Purpose: **Symmetric encrypt/decrypt**.  
6. Rotation: Every **90 days**.  

**Result:** The symmetric key was ready to encrypt and decrypt sensitive data efficiently.  

---

## Task 2: Create an Asymmetric Key  
Steps performed:  
1. Inside `demo-key-ring`, created a new key → `demo-asymmetric-key`.  
2. Chose **Software** protection.  
3. Key material: **Generated key**.  
4. Purpose: **Asymmetric decrypt**.  
5. Algorithm: Default asymmetric algorithm.  

**Result:** The asymmetric key pair was successfully created.  
- **Private key:** Used for decryption or signing.  
- **Public key:** Used for encryption or signature verification.  

---

## Key Insights  
- **Symmetric encryption** is **faster**, best for large data volumes.  
- **Asymmetric encryption** is **more secure** for key exchange and digital signatures.  
- In practice → Systems often **combine both**:  
  - Asymmetric keys establish trust (handshake).  
  - Symmetric keys handle bulk encryption.  

---

## Conclusion  
- Successfully created **both symmetric and asymmetric keys** in Google Cloud KMS.  
- Gained practical experience in **key generation, protection levels, and use cases**.  
- Learned how **cryptography underpins cloud data security**.  
- Ready to apply these techniques to real-world secure data storage and transmission scenarios.  

---

## Key Takeaways  
1. Symmetric = single key, **fast but key distribution is hard**.  
2. Asymmetric = key pair, **secure but slower**.  
3. Use a **combination** for best efficiency and security.  
4. Cloud KMS simplifies **key lifecycle management** (creation, rotation, usage).  

--- 
