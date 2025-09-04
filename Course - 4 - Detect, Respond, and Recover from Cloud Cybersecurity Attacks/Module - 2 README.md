# Cloud Security Monitoring, Threat Detection, and Response Frameworks

---

## Cyber Kill Chain® (Lockheed Martin)
- **Steps**: Reconnaissance → Weaponization → Delivery → Exploitation → Installation → Command & Control → Actions on Objectives  
- **Purpose**: Helps identify, analyze, and mitigate advanced persistent threats (APTs)  
- **Usefulness**: Provides defenders with a framework to detect, stop, or mitigate attacks at different stages  

---

## False Positives
- **Definition**: Alerts that incorrectly detect threats  
- **Causes**: Misconfigurations, over-engineered detection strategies  
- **Impact**: Leads to **alert fatigue** and wastes resources, increasing vulnerability  
- **Analysis**: Requires context, investigation, and remediation  

---

## Security Monitoring
- **Definition**: Continuous surveillance of systems to detect & respond to incidents  
- **Types**:  
  - *Proactive*: Ongoing monitoring (threat hunting, log analysis, IAM checks)  
  - *Reactive*: Responding after an issue arises  
- **Tools**:  
  - **Security Command Center (SCC)**: Centralized asset view, detects misconfigurations & threats  
  - **Cloud Logging**: Stores, searches, analyzes, and alerts on logs  
  - **Cloud Monitoring**: Collects metrics, events, insights  
  - **Chronicle (SIEM & SOAR)**: Log analysis, automated incident response  
  - **VirusTotal**: Scans files, URLs, domains, IPs for malicious content  

---

## Indicators of Compromise (IoCs)
- **Definition**: Observable evidence of potential security incidents (e.g., hash values, IP addresses, domains)  
- **Best Practices**:  
  1. Proactive monitoring  
  2. Thorough investigation  
  3. Risk assessment  
  4. Timely response  
  5. Documentation  
- **Tools**: Chronicle + VirusTotal + SCC help detect, analyze, and respond  

---

## Threat Hunting
- **Definition**: Proactive search for hidden or undetected threats  
- **Benefits**:  
  - Mitigates risks early  
  - Enables faster responses  
  - Informs business/security strategies  
- **Framework**: **MITRE ATT&CK®** → tactics (why), techniques (how), procedures (specific methods)  
- **Tools**: Chronicle (with ATT&CK mapping), ML/AI-based detection, alert prioritization, historical analysis  

---

## Aggregation & Correlation
- **Aggregation**: Collecting & consolidating logs/events from multiple sources  
- **Correlation**: Connecting related events to identify attack patterns  
- **Normalization**: Formatting raw data consistently for analysis  
- **Example Tool**: Chronicle SIEM (aggregates logs, correlates events, normalizes data)  

---

## Query Tools (RegEx & YARA-L)
- **RegEx**: Pattern matching for text & log analysis  
  - `.` = any character  
  - `\s` = whitespace  
  - `\d` = digit  
  - `[]` = character range  
- **YARA-L**: Language for creating detection rules in Chronicle  
  - *Best Practices*: Filter out zero values, add event-type filters  
- **Use**: Both help in searching logs & creating rules for threat detection  

---

## Key Takeaways
- Cyber Kill Chain® & MITRE ATT&CK® give frameworks for attack detection  
- False positives need careful management to avoid wasted effort  
- Cloud security relies on tools like SCC, Chronicle, Cloud Logging, Monitoring, and VirusTotal  
- IoCs + Threat Hunting strengthen proactive defense  
- Aggregation, correlation, normalization improve data analysis  
- RegEx & YARA-L are core querying tools for security professionals  

---

## Terms and Definitions 
- **Advanced persistent threat (APT)**: An adversary that possesses sophisticated levels of expertise, significant resources, and achieves its objectives through multiple attack vectors.  
- **Aggregation**: The process of collecting and consolidating diverse forms of data.  
- **Correlation**: The relationship between two or more security events.  
- **False positive**: An alert that incorrectly detects the presence of a threat.  
- **Indicators of compromise (IoC)**: Observable evidence that suggests signs of a potential security incident.  
- **MITRE ATT&CK®**: A framework used to understand and approach threats.  
- **Procedures**: The specific implementation of a technique.  
- **Regular expression (RegEx)**: A sequence of characters that forms a pattern.  
- **Security monitoring**: A systematic process of surveilling systems to detect and handle potential security breaches or incidents.  
- **Tactics**: A malicious actor's reason for performing an action or technique.  
- **Techniques**: The specific actions a malicious actor used to accomplish their goal.  
- **Threat hunting**: A proactive method of identifying previously unknown threats within a network.  
- **Unified data model (UDM)**: A data model used to process and store data.  
- **YARA-L**: A computer language used to create detection rules for searching through ingested log data.  
