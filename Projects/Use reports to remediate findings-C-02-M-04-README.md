# Use Reports to Remediate Findings

## Why Reports Matter

-   Highlight vulnerabilities, compliance gaps, misconfigurations.
-   Provide data-driven evidence for decisions.
-   Enable prioritization of remediation tasks.
-   Reduce risks of data breaches and non-compliance.

## Lab Context

**Scenario: Cymbal Bank** - Role: Cloud Security Analyst. - Task:
Review a management report with security findings. - Challenge:
Sensitive documents exposed in a misconfigured Cloud Storage bucket. -
Goal: Identify issues, remediate, confirm compliance.

## Lab Setup

**Environment & Requirements** - Google Cloud credentials. -
Security Command Center (SCC). - Cloud Storage bucket with


## Task 1: Identify Vulnerabilities

**Using Security Command Center (SCC)** - Navigate: **Security →
Overview → Vulnerabilities**. - Key findings: - **Public bucket ACL**
(high risk). - **Bucket policy only disabled** (medium risk). - **Bucket
logging disabled** (low risk -- ignored). - Compliance check: -
Confirmed active findings in CIS GCP Foundation 2.0 report.

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-01.png?raw=true)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-02.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-03.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-05.png)

---

## Task 2: Remediate Vulnerabilities

**Steps to Secure the Bucket** 1. Remove **public access (allUsers)**.
2. Switch to **uniform bucket-level access**. 3. Save and enforce new
permissions. 4. Run compliance report again.

Result: Findings for **Public bucket ACL** and **Bucket policy only**
dropped to **0**.

## Key Commands / Actions

**Console Actions** - Storage → Buckets → Permissions. - Remove
**allUsers** from *Storage Object Viewer*. - Switch **Access Control** →
Uniform. - Security → Compliance → Verify CIS report.

## Task Validation

**Verification Methods** - **Compliance Reports**: - CIS GCP Foundation
2.0 report. - Confirm zero active findings. - **SCC Dashboard**: -
Vulnerabilities list refreshed.

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-06.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-07.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-08.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-09.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-10.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-11.png)

![Use reports to remediate findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Use%20reports%20to%20remediate%20findings-12.png)

## Conclusion

**What I Achieved** - Identified risks using SCC. - Remediated
misconfigured Cloud Storage bucket. - Verified compliance via CIS
reporting. - Prevented potential **data breach / unauthorized access**.

## Key Learnings

**Takeaways for Security Practice** - Reports guide **priority-based
remediation**. - SCC centralizes findings across resources. - Compliance
frameworks (like CIS) are practical validation tools. - Timely
remediation = stronger security posture.

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  


