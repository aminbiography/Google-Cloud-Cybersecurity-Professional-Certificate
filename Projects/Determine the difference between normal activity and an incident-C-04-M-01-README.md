# Determine the Difference Between Normal Activity and an Incident

This guide presents a structured lab activity with text explanations **and images** in the right positions to illustrate each step. 

---

## Project Objective
The objective of this project is to **learn how to differentiate between normal and malicious activity** in a cloud environment by using **Google Cloud Security Command Center (SCC)** and **Event Threat Detection**. You will:
- Trigger IAM findings by granting roles.
- Investigate findings in SCC.
- Analyze related logs in Cloud Logging.
- Identify benign vs. malicious IAM activity.
- Remediate malicious findings by fixing IAM roles.

---

## Activity Overview
Event Threat Detection is one of Security Command Center's (SCC) services. It continuously monitors Google Cloud logs for potential threats and generates findings. In this lab, I’ll analyze findings and examine related logs.

![Cloud Overview](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-01.jpg)

---

## Scenario
- The security team discovered **two IAM anomalous grant findings**.
- One = **benign normal activity**.
- One = **malicious activity**.
- Objective: Learn to distinguish between normal and malicious IAM activity.

---

## Task 1: Grant Permissions to an External Account
- Navigate to **IAM & Admin > IAM**.
- Grant **Project Owner** rights to: `bad.actor.demo@gmail.com`.
- This will trigger an **Event Threat Detection finding**.

![IAM Permissions with external user](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-02.jpg)

Notes:
- **Users** (`qwiklabs.net`) with Owner roles = normal.
- **Gmail account** with Owner role = malicious.

---

## Task 2: Access the Event Threat Detection Findings
- Navigate to **Security > Findings**.
- Filter for **Persistence: IAM anomalous grant** findings.
- Review the severity (High/Medium/Low).

![SCC Findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-03.jpg)

---

## Task 3: Analyze the Findings
- **Earliest finding**:
  - Principal = `qwiklabs.net` service account → **benign**.
- **Latest finding**:
  - Principal = `bad.actor.demo@gmail.com` → **malicious**.

**Conclusion:**
- Internal org accounts = **normal**.
- External Gmail owner access = **incident**.

---

## Task 4: Access the Findings in Cloud Logging
- Use **Logs Explorer** with query:
  ```
  protoPayload.authorizationInfo.permission="resourcemanager.projects.setIamPolicy"
  protoPayload.methodName="InsertProjectOwnershipInvite"
  ```
- Review details like `authenticationInfo`, target user, IP, and browser.

![Logs Explorer general view](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-04.jpg)

![Logs Explorer anomalous request](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-05.jpg)

---

## Task 5: Fix the Finding
- Go back to **IAM > IAM**.
- Remove the **Project Owner** role from `bad.actor.demo@gmail.com`.
- Save policy → malicious access revoked.

![Remove malicious principal](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-06.jpg)

---

## Conclusion
I practiced:
- Identifying **normal vs. malicious IAM activity**.
- Investigating findings with **SCC**.
- Querying and analyzing logs with **Cloud Logging**.
- Remediating malicious activity by fixing IAM roles.

**Key Skill:** Rapidly distinguish between benign and malicious activity, investigate evidence, and take remediation steps to secure your cloud environment.

---

## Project Credit
- **Lab Activity & Prepared By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Lab Source**: Google Cloud Security Command Center hands-on lab (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  

