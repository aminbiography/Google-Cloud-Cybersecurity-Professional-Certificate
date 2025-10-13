# **Final Report Presentation: Respond and Recover from a Data Breach**

---

## **Project Title**

### **Cymbal Retail Cloud Security Incident: Respond and Recover from a Data Breach**

*A comprehensive review of Cymbal Retail’s cloud data breach and recovery response.*

---

![Respond and recover from a data breach - Security Incident Report - Capstone Project - Final Report](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-Security%20Incident%20Report-Capstone%20Project-Final%20Report.jpg)

---

## **Project Scenario**

Cymbal Retail, a leading cloud-based retail organization, experienced a **major cloud security incident** involving unauthorized access to its **Google Cloud Platform (GCP)** infrastructure. The breach originated from a compromised virtual machine (VM) named **cc-app-01**, which had **open RDP and SSH ports** and **disabled firewall logging**. These misconfigurations created a vulnerable entry point for an external threat actor.

The attacker exploited these weaknesses to gain unauthorized access, deploy malware, and escalate privileges by compromising a service account. The malicious actor then exfiltrated **sensitive customer payment information** through a publicly accessible Cloud Storage bucket.

This incident required a coordinated response effort from the security operations team to **contain the attack, eradicate the malicious presence, recover critical systems**, and implement stronger preventative controls. Following remediation, Cymbal Retail conducted a comprehensive post-incident review to identify gaps, document findings, and improve its cloud security posture.

---

## **Project Description**

This capstone project focuses on the **post-incident phase of the cybersecurity incident response lifecycle**, emphasizing **response, recovery, and continuous improvement** following a data breach in a cloud environment.

The report documents:

* The **Executive Summary** of the breach,
* Detailed **Response and Remediation** measures, and
* Strategic **Recommendations** for preventing similar incidents.

It integrates findings from the **Google Cloud Security Command Center (SCC)**, forensic investigations, and compliance assessments (ISO 27001, NIST 800-53, PCI DSS 3.2.1) to provide a structured and evidence-based conclusion to the incident.

This project demonstrates the application of professional **cloud incident handling standards** in accordance with the **NIST SP 800-61 Incident Response Framework** and **ISO/IEC 27035**.

---

## **Project Original URLs**

* [Data Breach Incident Details Document](https://docs.google.com/document/d/1Ua45FlrnhGglpvTYmskRZ9Exvu8JxEL56QeGgv4Gvdk/edit?usp=drive_link)
* [Security Incident Report Template and Investigation Summary](https://docs.google.com/document/d/1z2ubvD9o2BoNDdvl2i4oa0HDGzsiawtI1GBuAYPWuW8/edit?usp=drive_link)

---

## **Executive Summary**

Cymbal Retail suffered a **high-severity cloud security breach** that compromised sensitive customer data within its Google Cloud infrastructure. The attack stemmed from a vulnerable virtual machine (**cc-app-01**) with exposed RDP and SSH ports and no active firewall logging. These weaknesses allowed a malicious actor to gain initial access, deploy malware, and escalate privileges via a compromised service account.

The attacker leveraged this access to target **BigQuery datasets** and a **publicly accessible Cloud Storage bucket**, through which **payment card and user information** were exfiltrated.

Key resources affected included:

* **Compute Engine (cc-app-01)**
* **Firewall rules and network configurations**
* **Cloud Storage buckets**
* **BigQuery services**

The **Google Cloud Security Command Center (SCC)** revealed significant compliance gaps related to access control, configuration management, and monitoring. The breach highlighted the urgent need for **robust cloud configuration management**, **network security enforcement**, and **identity-based access controls**.

Immediate containment actions, combined with rapid remediation and long-term hardening measures, enabled the organization to restore integrity, strengthen resilience, and enhance compliance with key security frameworks.

---

## **Response and Remediation**

### **Containment and Eradication Measures**

1. **Isolated the compromised VM (cc-app-01)** to prevent further malicious activity and preserve forensic evidence.
2. **Disabled open RDP and SSH ports** and implemented restrictive firewall rules allowing access only through internal IP ranges and VPN.
3. **Enabled firewall rule logging** to regain full visibility into inbound and outbound network traffic.
4. **Revoked and rotated all compromised credentials** and service account keys exposed during the attack.
5. **Removed public access permissions** from all Cloud Storage buckets to prevent additional data leakage.
6. **Conducted full malware scans** across all Compute Engine instances to identify and eliminate residual malicious scripts.
7. **Enabled continuous threat detection and monitoring** using Google Cloud SCC and Cloud Logging.
8. **Validated eradication success** through integrity checks, forensic log reviews, and environment re-verification.

---

### **Recovery Measures**

1. **Provisioned a new hardened VM (cc-app-02)** configured without a public IP and with Secure Boot enabled.
2. **Restored validated clean backups** of affected applications and databases from pre-incident recovery points.
3. **Applied operating system and application patches** to address all known vulnerabilities.
4. **Implemented least privilege access policies (IAM)** and enforced **multi-factor authentication (MFA)** for all administrative accounts.
5. **Deployed continuous monitoring and automated alerts** through Cloud Monitoring and SCC for early detection of abnormal activities.
6. **Reassessed compliance posture**, achieving 100% alignment with OWASP 2021 and 87% with PCI DSS 3.2.1.
7. **Documented all response and recovery actions** to support audit and compliance requirements.
8. **Conducted a post-incident review** to identify process gaps and integrate lessons learned into the incident response plan.

---

## **Recommendations**

### **1. Enforce Strong Network Security Controls**

Adopt a **default-deny network policy** to restrict all inbound traffic unless explicitly authorized. Limit SSH/RDP access via **Identity-Aware Proxy (IAP)** or **VPN**, and ensure firewall logging remains permanently enabled. These measures reduce the external attack surface and improve audit traceability.

---

### **2. Secure Cloud Storage Configurations**

Enforce organization-wide **Cloud Storage access restrictions** that block all public permissions. Implement **Cloud Data Loss Prevention (DLP)** to scan for sensitive data and apply **Object Lifecycle Management** to control data exposure timeframes and retention policies.

---

### **3. Strengthen IAM and Credential Management**

Implement a **Zero Trust security model** emphasizing user verification and least privilege. Enforce MFA across all privileged accounts, rotate service keys regularly, and use **IAM Recommender** to eliminate excessive or unused permissions.

---

### **4. Enhance Continuous Monitoring and Incident Response**

Integrate **SCC findings** into automated incident response workflows for faster detection and mitigation. Conduct **quarterly penetration tests and red team exercises** to validate security controls. Use compliance dashboards to monitor configuration drift and vulnerability trends.

---

## **Project Conclusion**

Through swift containment, comprehensive remediation, and strengthened security governance, **Cymbal Retail successfully neutralized the breach**, restored operational integrity, and reinforced its overall cloud security resilience.

The incident demonstrated the importance of:

* **Continuous monitoring and proactive threat detection**
* **Regular configuration audits and compliance reviews**
* **Adherence to least privilege principles**
* **Comprehensive incident documentation and lessons learned**

By implementing the recommended security measures, Cymbal Retail has significantly improved its defensive posture, achieving measurable compliance gains and operational confidence. This experience serves as a model for effective **cloud-based incident response and recovery** within modern enterprise environments.

---

## **Project Credit**

- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation, NIST SP 800-61, ISO/IEC 27035 & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies. 

---
