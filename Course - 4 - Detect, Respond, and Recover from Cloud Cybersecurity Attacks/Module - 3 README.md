# Cloud Security Incident Response & Documentation

## **Incident Response Process**
- Three main phases:  
  1. **Identification** – recognize incidents with SIEM/SOAR alerts.  
  2. **Control** – limit damage, coordinate, communicate, restore operations.  
  3. **Iteration & Improvement** – learn from incidents, update processes, prevent recurrence.  
- Tools: **SOAR** (automation, coordination) and **SIEM** (log collection, analysis).  

---

## **Incident Identification**
- Triage & prioritize alerts by **severity, impact, urgency**.  
- Collect logs, traffic, user activity → assess scope & impact.  
- Differentiate **true incidents vs. false positives** using:  
  - **Analysis** (patterns, evidence).  
  - **Verification** (system compromise check).  

---

## **Coordination & Communication**
- Success relies on **clear roles**: Incident Manager, Lead Investigator, Communication Lead, Technical Specialists.  
- Must-have tasks: set goals, define responsibilities, establish comms channels, track progress, keep stakeholders informed.  
- High-quality communication: standardized terms, regular updates, secure channels.  

---

## 4. **Documentation Fundamentals**
- Types: **Incident reports, Evidence logs, Action plans, Playbooks, Logbooks**.  
- Qualities: **Accurate, clear, consistent, timely**.  
- Preserves evidence (file integrity, chain of custody).  
- Enables legal investigations & organizational learning.  
- Google Cloud tools (BigQuery, Chronicle SIEM) preserve evidence securely.  

---

## **Documentation Elements**
- **Incident summary** – overview, severity, context.  
- **Timeline** – chronological order of events.  
- **Technical findings** – logs, misconfigurations, IOCs.  
- **Actions taken** – steps to mitigate.  
- **Lessons learned** – review of what went well & failed.  
- **Recommendations** – improvements for future.  

---

## **Playbooks & SOAR**
- **Playbook**: reusable workflows for response (manual or automated).  
- Trigger → Action → Flow.  
- Benefits: saves time, ensures consistency, reduces risk, improves collaboration, supports compliance.  
- Best practices: clarity, modularity, maintenance, reusability, test regularly.  

---

## **Automation vs. Orchestration**
- **Automation** = task automation in a single system.  
- **Orchestration** = coordination across multiple systems/platforms.  
- Both are interdependent → automation forms part of orchestration processes.  

---

## **Incident Response Partners**
- **Chronicle SIEM/SOAR** – log ingestion, ML threat detection, automated playbooks.  
- **Mandiant** – breach analytics, hunting, threat intelligence, managed defense.  
- **VirusTotal** – enrich alerts with malware/IOC data.  
- **MITRE ATT&CK** – framework of tactics/techniques to model attacker behavior.  

---

## **Logs, Queries, and BigQuery**
- **Cloud Audit Logs** track admin activity (who, when, where).  
- **Log sinks** export logs (e.g., to BigQuery).  
- **BigQuery** enables large-scale log analysis with SQL.  
- Example use: detect deletions of VM instances in last 7 days.  

---

## **Evidence Preservation**
- Documentation: include **summary, timeline, actions, lessons**.  
- Maintain **chain of custody** (timeline, integrity, ownership).  
- Promptly collect evidence → cloud resources may be **ephemeral** or autoscaled.  
- Use encryption, access management, and secure storage.
- Prioritization: ask **severity, impact, urgency**.  
- **Iteration:** improve practices from past incidents.
---

---

## **Terms and definitions** 
- **Chain of custody:** The process of documenting and preserving evidence in a way that maintains its integrity, and establishes a clear timeline for handling
- **Incident:** A violation or imminent threat of violation of computer security policies, acceptable use policies, or standard security practices
- **Playbook:** A manual that provides details about any operational action
- **Security information and event management (SIEM):** An application that collects and analyzes log data to monitor critical activities in an organization
- **Security orchestration, automation, and response (SOAR):** A collection of applications, tools, and workflows that use automation to respond to security events


