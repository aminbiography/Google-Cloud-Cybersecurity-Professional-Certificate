
# **Final Report Presentation: Respond and Recover from a Data Breach**

---

## **Project Title** **Cymbal Retail Cloud Security Incident: Respond and Recover from a Data Breach**

---

![Respond and recover from a data breach-Security Incident Report-Capstone Project-Final Report](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-Security%20Incident%20Report-Capstone%20Project-Final%20Report.jpg)

---

## **Project Scenario**

Cymbal Retail, a cloud-based retail company, experienced a significant **data breach** involving unauthorized access to its Google Cloud environment. The attack targeted a compromised virtual machine (VM), **cc-app-01**, which had open RDP and SSH ports and lacked firewall logging. This misconfiguration allowed a malicious actor to infiltrate the system, escalate privileges, and exfiltrate sensitive customer payment data.

The incident required immediate response efforts to contain the threat, eradicate the attacker’s presence, and restore secure cloud operations. Following recovery, Cymbal Retail focused on strengthening its cloud defenses and documenting the incident for lessons learned.

---

## **Project Description**

This project demonstrates the **post-incident response phase** of the cloud security lifecycle, focusing on the actions taken to **respond, recover, and improve security posture** after a data breach.

The report includes an **Executive Summary**, **Response and Remediation** actions, and **Recommendations** for future prevention.
It draws upon forensic analysis, Google Cloud Security Command Center findings, and compliance metrics (ISO 27001, PCI DSS, NIST 800-53) to ensure a structured and compliant incident closure.

---

## **Project Original URLs**

* [Data Breach Incident Details Document](https://docs.google.com/document/d/1Ua45FlrnhGglpvTYmskRZ9Exvu8JxEL56QeGgv4Gvdk/edit?usp=drive_link)
* [Security Incident Report Template and Investigation Summary](https://docs.google.com/document/d/1z2ubvD9o2BoNDdvl2i4oa0HDGzsiawtI1GBuAYPWuW8/edit?usp=drive_link)

---

## **Executive Summary**

Cymbal Retail experienced a **critical cloud security incident** when attackers exploited open RDP and SSH ports on VM **cc-app-01**, which lacked proper firewall controls and logging. The attacker gained unauthorized access, installed malware, and escalated privileges using a compromised service account.

Subsequent investigation revealed **data exfiltration** from a publicly accessible Cloud Storage bucket containing sensitive customer data, including credit card details.

The most impacted cloud resources included:

* **Compute Engine (cc-app-01)**
* **Firewall configurations**
* **Cloud Storage buckets**
* **BigQuery datasets**

Key compliance gaps were found in **access control**, **logging**, and **configuration management**. The incident underscored the necessity of **continuous monitoring**, **secure configurations**, and **strong identity management** to prevent similar breaches.

---

## **Response and Remediation**

### **Containment and Eradication Measures**

1. **Isolated compromised VM (cc-app-01)** to stop malicious activity and preserve forensic evidence.
2. **Closed open RDP/SSH ports** and enforced strict firewall rules limiting access through internal IPs and VPNs only.
3. **Enabled firewall logging** for full visibility into inbound/outbound network traffic.
4. **Revoked compromised credentials** and regenerated secure service account keys.
5. **Removed public access** from all Cloud Storage buckets and implemented organization-wide access restrictions.
6. **Scanned all compute resources** for residual malware and unauthorized processes.
7. **Activated continuous threat monitoring** through Google Cloud Security Command Center (SCC).
8. **Validated cleanup success** via fresh scans, log reviews, and integrity verification.

---

### **Recovery Measures**

1. **Rebuilt secure VM (cc-app-02)** using hardened configurations and no public IP assignment.
2. **Restored clean backups** of data and services verified from pre-incident snapshots.
3. **Applied OS and application patches** to remove known vulnerabilities.
4. **Implemented IAM least privilege policies**, ensuring each user and service has minimal required permissions.
5. **Deployed multi-factor authentication (MFA)** across all privileged accounts.
6. **Configured continuous monitoring** with Cloud Logging, SCC, and automated alerting for high-severity findings.
7. **Performed compliance validation**, achieving 100% OWASP 2021 compliance and 87% PCI DSS 3.2.1 adherence.
8. **Documented incident response procedures** for audit and training purposes.

---

## **Recommendations**

### **1. Enforce Strong Network Security Controls**

Apply a **default-deny firewall policy**, allowing only authorized traffic. Restrict administrative access (SSH/RDP) through **Identity-Aware Proxy (IAP)** or **VPN**. Maintain permanent firewall logging for all inbound/outbound connections.

---

### **2. Secure Cloud Storage Configurations**

Prohibit public access to all storage buckets organization-wide. Use **Cloud Data Loss Prevention (DLP)** tools to detect sensitive data and enforce **Object Lifecycle Management** to prevent prolonged exposure of critical files.

---

### **3. Strengthen IAM and Credential Management**

Adopt a **zero-trust access model** enforcing MFA, credential rotation, and role-based access control (RBAC). Use **IAM Recommender** to identify and remove unused permissions and enforce least privilege principles.

---

### **4. Improve Continuous Monitoring and Incident Response**

Integrate SCC alerts with the **incident response workflow** for faster detection and action. Conduct quarterly red team exercises, and automate vulnerability scans with compliance dashboards for proactive security assurance.

---

## **Project Conclusion**

Through rapid containment, methodical remediation, and strengthened governance, Cymbal Retail **eradicated the threat**, restored full operational integrity, and reinforced its cloud security posture.

The incident emphasized the need for:

* Continuous **security monitoring**
* Rigorous **configuration management**
* Comprehensive **incident documentation**

Cymbal Retail’s proactive actions have significantly enhanced resilience against future threats, aligning its operations with cloud security best practices and compliance frameworks.

---

## **Project Credit**

- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies. 
