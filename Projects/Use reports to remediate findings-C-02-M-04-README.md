
# Use Reports to Remediate Findings  

This presentation-style README includes step-by-step remediation tasks with screenshots.  

---

## Lab Overview  
- **Level**: Introductory  
- **Focus**: Cybersecurity, compliance, and cloud storage remediation using **Google Cloud Security Command Center (SCC)**.  

Reports highlight vulnerabilities, issues, or non-compliance with standards. Acting on them helps mitigate risks, prevent breaches, and strengthen overall security posture.  

---

## Scenario  
Your task: Remediate findings reported by the **Security Command Center (SCC)** regarding a **misconfigured Cloud Storage bucket**.  

**Threats identified:**  
- Sensitive documents stored in a **publicly accessible bucket**.  
- **Uniform bucket-level access disabled**.  
- **Bucket logging disabled** (low risk, not required to remediate in this lab).  

---

## Setup Instructions  
1. Launch the lab from Coursera → Qwiklabs.  
2. Open **Google Cloud Console** in an **Incognito Window**.  
3. Log in with **temporary credentials** provided in the Lab Details panel.  
   - Accept terms.  
   - Do **not** add recovery options or free trials.  

---

## Task 1: Identify Vulnerabilities with SCC  
1. In the **Google Cloud Console**, go to:  
   `Navigation Menu → Security → Overview`  
2. Open **Vulnerabilities** to review findings.  

**Key Active Findings**:  
- **PUBLIC_BUCKET_ACL** → Bucket is publicly accessible (High risk).  
- **BUCKET_POLICY_ONLY_DISABLED** → Uniform bucket access disabled (Medium risk).  
- **BUCKET_LOGGING_DISABLED** → Logging disabled (Low risk ).  

**Screenshot Example**  
![Findings in SCC](d6a98599-ad85-4346-84da-a7a3d675e49f.png)  

---

## Task 2: Remediate Vulnerabilities  

### 1. Remove Public Access  
- Go to: `Cloud Storage → Buckets → [Your Bucket] → Permissions`.  
- Expand **Storage Object Viewer** role.  
- Remove **allUsers**.  

**Screenshot**  
![Remove public access](faea252d-4c8e-46f8-ac00-cf6579da23a5.png)  

### 2. Enforce Uniform Access Control  
- In the **Access control tile**, click: **Switch to uniform** → Save.  

**Screenshot**  
![Switch to uniform access](16241cc1-b2b4-4f08-b3c7-a6c69a162849.png)  

### 3. Verify Remediation  
- Return to **Security → Compliance → CIS GCP Foundation 2.0 Report**.  
- Confirm that active findings for:  
  - *Public bucket ACL* = **0**  
  - *Bucket policy only disabled* = **0**  

**Compliance Screenshot**  
![Compliance status](d8666305-921f-459b-80c4-b0575f4727d7.png)  
![Compliance details](dea1dccd-ca43-45a6-b47c-179b989f235a.png)  

---

## 🏁 Conclusion  
Identified and prioritized threats using **Security Command Center (SCC)**.  
Remediated:  
- Public bucket ACL issue.  
- Disabled bucket policy issue.  
Confirmed remediation with a **compliance report**.  

**Result:** Your organization is now better protected against unauthorized access, data breaches, and data loss.  

---

## Key Takeaways  
- Always act quickly on **high-risk findings**.  
- Use **uniform bucket-level access** for consistent permissions.  
- Regularly run **compliance reports** to maintain security posture.  

---

© 2024 Google LLC. All rights reserved.  
