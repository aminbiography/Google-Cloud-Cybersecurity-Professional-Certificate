# Determine the Difference Between Normal Activity and an Incident

---

## Project Objective
The objective of this project is to **learn how to differentiate between normal and malicious activity** in a cloud environment by using **Google Cloud Security Command Center (SCC)** and **Event Threat Detection**.  

In this project I:  
- Triggered IAM findings by granting roles.  
- Investigated findings in SCC.  
- Analyzed related logs in Cloud Logging.  
- Identified benign vs. malicious IAM activity.  
- Remediated malicious findings by fixing IAM roles.  

---

## Activity Overview
Event Threat Detection is one of Security Command Center's (SCC) services. It continuously monitors Google Cloud logs for potential threats and generates findings.  
In this lab, **I analyzed findings and examined related logs**.  

![Cloud Overview](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-01.jpg)

---

## Scenario
Recently, the security team discovered **two IAM anomalous grant findings**.  
- One was identified as **benign normal activity**.  
- One was confirmed as **malicious activity**.  

My task was to recreate the suspicious activity, analyze the findings, and take remediation actions.  

---

## Task 1: Grant Permissions to an External Account
- I navigated to **IAM & Admin > IAM**.  
- I granted **Project Owner** rights to: `bad.actor.demo@gmail.com`.  
- This action triggered an **Event Threat Detection finding**.  

![IAM Permissions with external user](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-02.jpg)

**Notes:**  
- Users from `qwiklabs.net` with Owner roles = **normal activity**.  
- An external Gmail account with Owner role = **malicious activity**.  

---

## Task 2: Access the Event Threat Detection Findings
- I opened **Security > Findings** in SCC.  
- I filtered for **Persistence: IAM anomalous grant** findings.  
- I reviewed their severity levels.  

![SCC Findings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-03.jpg)

---

## Task 3: Analyze the Findings
- **Earliest finding**:  
  - Principal = `qwiklabs.net` service account → **benign**.  
- **Latest finding**:  
  - Principal = `bad.actor.demo@gmail.com` → **malicious**.  

**Conclusion:**  
- Internal organization accounts = **normal**.  
- External Gmail with Owner role = **incident**.

![Logs Explorer general view](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-04.jpg)   

---

## Task 4: Access the Findings in Cloud Logging
I queried the logs in **Logs Explorer** with:  

```sql
protoPayload.authorizationInfo.permission="resourcemanager.projects.setIamPolicy"
protoPayload.methodName="InsertProjectOwnershipInvite"
```

This returned IAM log events for anomalous owner grants.  

- I reviewed details like:  
  - `authenticationInfo`: who made the request.  
  - `request`: which user was granted access.  
  - Metadata: IP address and browser details.  

![Logs Explorer anomalous request](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-05.jpg)  

---

## Task 5: Fix the Finding
- I returned to **IAM > IAM**.  
- I removed the **Project Owner** role from `bad.actor.demo@gmail.com`.  
- I saved the updated IAM policy → malicious access revoked.  

![Remove malicious principal](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Determine%20the%20difference%20between%20normal%20activity%20and%20an%20incident-06.jpg)

---

## Conclusion
Through this project, I practiced:  
- Distinguishing **normal vs. malicious IAM activity**.  
- Investigating findings using **SCC**.  
- Analyzing logs with **Cloud Logging**.  
- Remediating threats by fixing IAM roles.  

**Key Skill:** I developed the ability to quickly detect whether activity is benign or malicious, investigate it using logs, and take corrective actions to secure the environment.  

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  

