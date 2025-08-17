# Cloud Security Risks: Data Protection

## Asymmetric vs Symmetric Encryption
- **Symmetric:** Uses a single secret key for both encryption and decryption. It is fast and efficient, but key distribution is a challenge because sharing the same key introduces risks. Commonly used in bulk data encryption.  
- **Asymmetric:** Uses a public/private key pair. The public key encrypts data, while the private key decrypts it. It’s more secure for sharing across untrusted networks but slower compared to symmetric encryption. Often used in digital signatures and secure key exchanges.  

## Data Discovery & Governance
- **Data discovery:** The process of exploring, analyzing, and mapping organizational data to reveal hidden patterns, insights, and sensitive information that needs protection.  
- **Governance:** Establishes rules and policies to ensure data is accurate, complete, and accessible only to authorized users. Helps organizations remain compliant with regulations.  
- **Tags:** Metadata labels that classify, categorize, and document data. Tags make it easier to manage, monitor, and secure sensitive data across systems.  

## Business Continuity Planning (BCP)
- A proactive strategy that ensures essential business operations continue during crises such as cyberattacks, natural disasters, or system outages.  
- **Benefits:**  
  - Minimizes financial losses caused by unexpected disruptions.  
  - Protects the company’s brand and reputation.  
  - Provides structured recovery processes, ensuring critical services are restored quickly.  

## Data Regulations
- **Data Sovereignty:** Data must comply with the laws of the country where it is created or processed.  
- **Data Localization:** Legal requirement that data must stay physically within a country’s borders.  
- **Data Residency:** Refers to the physical or geographic location where an organization’s data is stored, which often influences compliance and performance.  

## Cloud Security Concepts
- **Identity Management & Access Control:** Ensures the right individuals have the right access to resources, enforcing principles like least privilege.  
- **Security Models:**  
  - *Traditional Perimeter Security* relies on firewalls and boundaries.  
  - *Zero Trust Model* assumes no implicit trust, verifying every request regardless of source.  
- **Threat & Vulnerability Management:** Includes asset discovery, patching, remediation, and posture management to strengthen defenses.  
- **Cloud-Native Principles:**  
  - *Ephemerality & Immutability:* Systems are temporary and non-editable, reducing risks of tampering.  
  - *Rehydration & Reinstantiation:* Rapid rebuilding of environments to maintain resilience.  
- **Infrastructure as Code (IaC) & Policy as Code (PaC):** Automating security into cloud infrastructure and enforcing compliance policies programmatically.  
- **Containerization & Orchestration Security:** Protects containerized applications and their orchestrators (e.g., Kubernetes) against threats while ensuring scalability and consistency.  

