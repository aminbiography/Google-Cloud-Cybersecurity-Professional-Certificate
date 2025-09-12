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
- **11:46 a.m. — The Click**  
- **11:47 a.m. — The Credentials Stolen**  
- **11:48 a.m. — The Alarm Sounds**  
- **11:49 a.m. — The Breach Expands**  

![Timeline of Events](https://raw.githubusercontent.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/main/bar-graph-chart-image/Document%20a%20timeline%20of%20events.jpg)  

------------------------------------------------------------------------  

## Technical Findings  

- **Compromised Account**: Employee ID - 0131, submitted credentials to a phishing page.  
- **Unauthorized Access**: Attacker logged into 4 SaaS/cloud applications.  
- **Source Indicators**:  
  - Unrecognized device fingerprint  
  - Geolocation outside corporate IP ranges  
  - Multiple failed login attempts prior to success  

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

- **Detection**: SIEM alert, unusual login location/device  
- **Containment**: Disabled account, password reset, revoked sessions  
- **Eradication & Recovery**: Removed OAuth tokens, log review, monitoring  
- **Lessons Learned**: Phishing awareness gap, MFA not enforced  

------------------------------------------------------------------------  

## Indicators of Compromise (IOCs)  

| Type | Indicator | Description |  
|------|-----------|-------------|  
| IP Address | 185.203.112.45 | Source of suspicious login from Eastern Europe |  
| Domain | auth-secure-login[.]com | Phishing site hosting fake login page |  
| Email | noreply@securebank-alert[.]com | Sender address spoofed in phishing campaign |  
| Device ID | WIN10-unknown-8743 | Unrecognized endpoint fingerprint |  

*(Note: IOCs are anonymized for training purposes in this exercise.)*  

------------------------------------------------------------------------  

## Business Impact Assessment  

- **Systems Affected**: Four cloud-based applications accessed (internal comms, HR portal, finance dashboard, document repository).  
- **Data Accessed**: No confirmed exfiltration; attacker activity limited to login and session initiation.  
- **Risk Level**: High — credentials compromised, potential lateral movement possible if not contained quickly.  
- **Operational Impact**: Minimal downtime; remediation actions completed within 2 hours.  
- **Reputation Risk**: Executive team notified; incident could undermine customer trust if repeated.  

------------------------------------------------------------------------  

## Compliance & Regulatory Considerations  

- **GDPR**: No customer personal data confirmed as exfiltrated, but monitoring required to ensure compliance.  
- **PCI DSS**: Payment systems not accessed; no cardholder data exposure.  
- **Internal Policies**: Incident triggered mandatory review under Cymbal Bank’s Cloud Security Policy.  
- **Future Obligation**: If similar incidents occur with confirmed data exposure, regulatory disclosure may be required within **72 hours**.  

------------------------------------------------------------------------  

## Strategic Recommendations  

1. **Phishing Awareness Program**  
   - Launch quarterly phishing simulation tests for employees.  
   - Mandatory annual security awareness training.  

2. **Zero Trust & MFA**  
   - Enforce Multi-Factor Authentication across all applications.  
   - Deploy Conditional Access policies (block logins from high-risk geolocations).  

3. **Enhanced Monitoring**  
   - Correlate phishing indicators in SIEM with endpoint and identity logs.  
   - Implement UEBA (User and Entity Behavior Analytics) to detect abnormal patterns.  

4. **Incident Playbooks**  
   - Develop phishing-specific playbook integrated into SOAR platform.  
   - Automate disabling of accounts when multiple suspicious events are detected.  

------------------------------------------------------------------------  

## Project References  

- [Alert Ticket and Technical Findings](https://docs.google.com/document/d/1r7bVLey_-rMWyHXY0khA9rzvU9upQfXulaWydG_lyss/edit?usp=sharing)  
- [Google Slides Presentation](https://docs.google.com/presentation/d/1NH8kEaiHtzT2rJi8aIjweUn8bVkwb-xazIm7zJvAzvg/edit?usp=sharing)  

------------------------------------------------------------------------  

## Project Conclusion  

This incident highlights the critical importance of **speed in detection and response**. The attacker successfully compromised credentials and accessed multiple systems within minutes.  

**Key Lessons Learned:**  
- Human error (phishing click) remains the weakest link.  
- Real-time monitoring and MFA are critical safeguards.  
- IOC tracking and ATT&CK mapping enhance detection/response maturity.  
- Compliance and regulatory obligations must be factored into response strategy.  

By applying these lessons, Cymbal Bank can improve resilience, protect customer data, and strengthen trust in its cloud security.  

------------------------------------------------------------------------  

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Coursera)  
- **Guidance & Framework**: Google Cloud documentation & MITRE ATT&CK Framework  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
