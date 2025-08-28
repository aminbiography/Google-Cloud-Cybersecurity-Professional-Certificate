# Cloud Security Detection & Incident Response

---

## 1. Logging & Log Management
- **Logging**: Recording of events in systems/networks.  
- **Log analysis**: Examining logs for patterns, errors, threats.  
- **Log management**: Collecting, storing, analyzing, and disposing of logs.  
- **Retention policies**: Ensure compliance and historical analysis.  
- **Types of Google Cloud logs**:
  - **Admin activity** – tracks admin actions.  
  - **Data access** – records access to user data.  
  - **System event** – system configuration changes.  
  - **Policy denied** – unauthorized access attempts.  

---

## 2. Workplace Skills for Cloud Security
- **Attention to detail** → Spot anomalies in logs.  
- **Critical thinking** → Analyze data, find root cause.  
- **Time management** → Prioritize log monitoring & other tasks.  
- **Communication** → Report findings clearly, collaborate with teams.  
- **Adaptability & curiosity** → Stay updated on new threats/tools.  
- **Tools (SIEM & SOAR)** → Enhance skills with automation, alerts, collaboration.  

---

## 3. Alerts & Notifications
- **Alerts** = Real-time warnings about potential threats.  
- **Common alert types**:
  - Unusual network traffic  
  - Suspicious logins  
  - Policy violations  
- **False positives** = Normal activity flagged as threat.  
- **Alert fatigue** = Too many alerts overwhelm analysts.  
- **Best practices**:
  - Refine parameters  
  - Audit regularly  
  - Collaborate across teams  
  - Apply automation & training  
  - Customize strategies  

---

## 4. Querying Alerts
- **Definition**: Scanning/filtering alerts to find threats.  
- **Effective querying** reduces noise & prioritizes real threats.  
- **Common filters**: source, destination, severity, time.  
- **Best practices**:
  - Be specific but not too narrow.  
  - Save frequent searches.  
  - Track timing & frequency.  
  - Update filters regularly.  

---

## 5. Alert & Log Optimization
- **Cloud Monitoring** collects metrics like CPU, memory, traffic.  
- **Alerting policies**:
  - **Metric-based** → e.g., trigger alert if CPU > 80%.  
  - **Log-based** → e.g., alert if IAM key accessed.  
- **Metrics** improve incident response & system health.  
  - **Security metrics**: failed logins, unusual activity, triggered alerts.  
  - **Ops metrics**: CPU, memory, disk, API errors.  
- **Challenges**: false positives & alert fatigue → solved via noise reduction & automation.  

---

## 6. Event Threat Detection (ETD)
- **Part of Google Cloud SCC (Security Command Center)**.  
- **Continuously analyzes logs** for threats.  
- **Findings include**: category, severity, exposure score, timestamps, resource info.  
- **IAM anomalous grant detector**: flags unusual permission grants (e.g., external account made owner).  
- **Logs Explorer**: shows who granted access, to whom, and from where.  
- **Key takeaway**: Differentiate normal vs malicious activity.  

---

## 7. Incident Management Process
- **Phases**:
  1. Preparation  
  2. Detection  
  3. Containment  
  4. Eradication  
  5. Recovery  
  6. Lessons Learned  
- **Containment/Eradication** = isolate systems, remove unauthorized access.  
- **Goal**: Minimize damage & restore operations quickly.  

---

## 8. Red vs Blue Teams
- **Red Team**: Ethical hackers simulate attacks.  
- **Blue Team**: Defenders protect systems.  
- **Penetration Testing**: Red team simulates attacks to find vulnerabilities.  
- **Tabletop Exercises**: Scenario-based simulations for practice.  

---

## 9. Tools Overview
- **Chronicle SIEM**: Turns machine data into actionable security insights; improves alert filtering & querying.  
- **Chronicle SOAR**: Automates alert management, incident response playbooks, collaboration.  
- **SCC (Security Command Center)**: Centralized vulnerability and threat monitoring.  
- **Cloud Logging & Monitoring**: Tracks activity & metrics for incidents.  

---

## 10. Key Concepts (Glossary Highlights)
- **False Positive**: Alert incorrectly detecting a threat.  
- **Querying Alerts**: Searching alerts for real threats.  
- **SecOps**: Combines people, processes, and tech to protect systems.  
- **Anomaly-based detection**: Detects deviations from baseline activity.  
- **Vulnerability Management**: Finding & patching weaknesses.  

---

## Key Takeaway
Cloud security depends on strong **logging, alerting, querying, and incident response processes**, supported by workplace skills and automation tools like **SIEM, SOAR, and SCC**.  

