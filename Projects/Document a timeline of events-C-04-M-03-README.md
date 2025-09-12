
# Project Title: Phishing Incident Timeline Documentation  

------------------------------------------------------------------------  

## Project Scenario  

- On October 12, 2023, Cymbal Bank experienced its first severe phishing attempt since adopting cloud services.  
  An employee received a phishing email disguised as an authentication request, clicked the malicious link, and submitted credentials into a fake form.  

- The attacker immediately used the stolen credentials to access multiple applications, triggering alerts and suspicious activity logs.  
  This scenario highlights the speed at which phishing incidents escalate and the importance of effective detection, response, and prevention measures.  

------------------------------------------------------------------------  

## Project Objective  

The objective of this project is to document and visually present the timeline of a phishing incident at Cymbal Bank. This documentation ensures that executive stakeholders clearly understand the sequence of events, the speed at which the incident unfolded, and the importance of reinforcing security awareness and response processes.  

------------------------------------------------------------------------  

## Project Description  

[Alert Ticket and Technical Findings](https://docs.google.com/document/d/1r7bVLey_-rMWyHXY0khA9rzvU9upQfXulaWydG_lyss/edit?usp=sharing) — Full technical report including logs, timestamps, and details of the incident.  

On **October 12, 2023**, Cymbal Bank faced its first severe phishing attempt after adopting cloud services. The attack unfolded rapidly, with every minute escalating the risk. Below is a **step-by-step visual walk-through** of the incident:  

- **11:45 a.m. — The Hook is Set**  
  The user receives a phishing email. It appears authentic, disguised as a routine authentication request, but it contains a malicious link.  

- **11:46 a.m. — The Click**  
  The user, believing the email is legitimate, clicks on the phishing link. This action opens a fraudulent web page crafted to mimic a trusted login portal.  

- **11:47 a.m. — The Credentials Stolen**  
  The user submits their cloud login credentials into the fake form. Instantly, the attacker captures these details, gaining the keys to the bank's cloud services.  

- **11:48 a.m. — The Alarm Sounds**  
  Cymbal Bank's security systems detect an unusual login attempt: a new device connecting from an unfamiliar location. A high-severity alert is triggered, flagging potential compromise.  

- **11:49 a.m. — The Breach Expands**  
  Within seconds, the attacker leverages the stolen credentials to log into **four separate applications**. Suspicious activities spike across multiple platforms, confirming unauthorized access.  

![Timeline of Events](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Document%20a%20timeline%20of%20events.jpg)  

This **five-minute chain of events** illustrates how quickly a phishing attack can escalate from a single email to widespread unauthorized access.  

------------------------------------------------------------------------  

## Technical Findings (Advanced)  

- **Compromised Account**: Lucas (employee) submitted credentials to a phishing page.  
- **Unauthorized Access**: Attacker logged into 4 SaaS/cloud applications.  
- **Source Indicators**:  
  - Unrecognized device fingerprint.  
  - Geolocation: outside corporate IP ranges.  
  - Multiple failed login attempts prior to success.  
- **Attack Vector**: Credential harvesting via phishing email + fake login page.  

------------------------------------------------------------------------  

## MITRE ATT&CK Mapping  

| Step | Description | ATT&CK Technique | ID |  
|------|-------------|------------------|----|  
| 1 | User receives phishing email | Phishing for Information | **T1566.002** |  
| 2 | User clicks malicious link | User Execution: Malicious Link | **T1204.001** |  
| 3 | Credentials entered in fake form | Credential Phishing | **T1566.001** |  
| 4 | Attacker logs in with stolen credentials | Valid Accounts | **T1078** |  
| 5 | Suspicious activity in multiple applications | Use of Valid Accounts for Persistence | **T1078.004** |  

------------------------------------------------------------------------  

## Incident Response Actions  

- **Detection**:  
  - Real-time alert triggered by unusual login location/device.  
  - Security Information and Event Management (SIEM) logged the abnormal activity.  

- **Containment**:  
  - Disabled the compromised user account.  
  - Forced password reset for affected user.  
  - Revoked active sessions across all cloud applications.  

- **Eradication & Recovery**:  
  - Removed attacker persistence by reviewing OAuth tokens and application sessions.  
  - Conducted log analysis to confirm scope of access.  
  - Monitored applications for residual activity.  

- **Lessons Learned**:  
  - Identified lack of phishing awareness as primary cause.  
  - Gaps in MFA enforcement allowed attacker to succeed with credentials alone.  

------------------------------------------------------------------------  

## Project References  

- [Alert Ticket and Technical Findings](https://docs.google.com/document/d/1r7bVLey_-rMWyHXY0khA9rzvU9upQfXulaWydG_lyss/edit?usp=sharing) — Technical report containing timestamps, login details, user impact.  
- [Google Slides Presentation](https://docs.google.com/presentation/d/1NH8kEaiHtzT2rJi8aIjweUn8bVkwb-xazIm7zJvAzvg/edit?usp=sharing) — Slide deck designed for executive stakeholders summarizing the incident.  

------------------------------------------------------------------------  

## Project Conclusion  

This incident highlights the critical importance of **speed in detection and response**. The attacker successfully compromised credentials and accessed multiple systems within minutes.  

**Key Lessons Learned:**  
- **Employee vigilance** is the first line of defense — phishing awareness training must be strengthened.  
- **Real-time monitoring** and automated alerts are essential to flag suspicious behavior immediately.  
- **Multi-factor authentication (MFA)** should be enforced to prevent stolen credentials from being enough for account compromise.  
- **Mapping attacks to MITRE ATT&CK** provides valuable insight into attacker tactics and enables better defense-in-depth strategies.  

By applying these lessons, Cymbal Bank can improve resilience, protect customer data, and strengthen trust in its cloud security.  

------------------------------------------------------------------------  

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Coursera)  
- **Guidance & Framework**: Google Cloud documentation & MITRE ATT&CK Framework  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
