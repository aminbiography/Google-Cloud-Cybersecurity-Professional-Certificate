# The Capstone Project**

### **Overview**

*The Capstone Project* is the final module in the **Google Cloud Cybersecurity Certificate** program. It brings together everything you’ve learned across the previous courses, allowing you to apply your **cloud security knowledge and technical skills** to a realistic, hands-on security scenario.

In this module, you’ll step into the role of a **cloud security analyst** and respond to a simulated **data breach** at a fictional organization, *Cymbal Retail*. The project challenges you to analyze the incident, contain threats, remediate vulnerabilities, and create a detailed incident report. This experience mirrors the kind of work you’ll perform in professional cybersecurity roles and serves as a **portfolio-ready project** to demonstrate your job-readiness.

---

### **Learning Objectives**

By the end of this module, able to:

1. Apply **incident response techniques** to detect, contain, and remediate cloud-based security incidents.
2. Identify and fix misconfigurations in **Compute Engine VMs, Cloud Storage buckets, and firewall rules**.
3. Verify compliance with frameworks like **PCI DSS 3.2.1**.
4. Communicate findings effectively through a structured **security incident report**.
5. Present your project as a **portfolio artifact** to potential employers.

---

### **Capstone Scenario Summary**

**Organization:** Cymbal Retail
**Incident:** A major **data breach** resulting from multiple cloud security misconfigurations.
**Affected Systems:**

* **VM (cc-app-01)** – Public IP, open SSH/RDP ports, malware infection, default service account with full API access.
* **Cloud Storage Bucket** – Public access enabled, weak access controls, logging disabled.
* **Firewall Rules** – Open ports (22, 3389) and no logging enabled.

**Attack Path Overview:**

1. Attacker discovered open ports on VM `cc-app-01`.
2. Gained access through brute-force attack.
3. Installed malware to maintain persistence.
4. Compromised service account credentials to escalate privileges.
5. Accessed BigQuery and exfiltrated unencrypted credit card data via a public storage bucket.

---

### **Response and Remediation**

**Containment & Eradication:**

* Isolated the infected VM (`cc-app-01`).
* Restricted SSH and RDP access via updated firewall rules.
* Removed public access from the storage bucket and enabled **uniform bucket-level control**.

**Recovery:**

* Rebuilt VM (`cc-app-02`) from a **trusted snapshot**.
* Reviewed and hardened configurations across all cloud resources.
* Enabled **real-time monitoring and firewall logging** to detect future threats.

These actions successfully contained the incident and restored system integrity.

---

### **Recommendations for Future Prevention**

* Conduct **regular risk assessments and penetration testing**.
* Enable **Multi-Factor Authentication (MFA)** for all users.
* Enforce **least privilege principles** in IAM configurations.
* Maintain **continuous monitoring and compliance reviews**.
* Keep **logs and alerts** active for all cloud assets.

---

### **Final Deliverables**

* **Security Incident Report** – Documents the breach, response, and recommendations.
* **Final Report Activity** – Summarizes findings for stakeholders and post-incident analysis.
* **Portfolio Integration** – Adds your project to an online platform (GitHub, Google Sites, or Drive) as a showcase of your applied cybersecurity expertise.

---

### **Integrating the Project into Portfolio**

**Capstone Project** is a professional showcase technical capabilities.
**Steps to feature it effectively:**

* Add **technical skills** (e.g., risk management, threat detection, GCP tools) to your resume.
* Create a **Cloud Security Projects** section highlighting deliverables like incident reports and audit documents.
* Host portfolio online using:

  * [GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
  * [GitLab](https://gitlab.com/users/sign_up)
  * [Google Sites](https://support.google.com/sites/answer/6372878?hl=en&ref_topic=7184580)
  * [Google Drive](https://drive.google.com/corp/drive/my-drive)
* Include each project’s **title**, **overview**, **tools used**, and **key outcomes**.

---

### **Career Connection**

Completing this module prepares for **entry-level roles** such as:

* *Cloud Security Analyst*
* *Cybersecurity Associate*
* *Cloud Security Engineer*

---

### **Key Takeaways**

The Capstone Project consolidates all cloud cybersecurity concepts from the certificate.
Gained experience in **incident response, remediation, and compliance**.
A **portfolio-ready project** to showcase skills.
Continuous learning and portfolio updates will help stay competitive and career-ready.

---

