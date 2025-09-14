# Cloud Security Incident Response & Documentation

## Incident Response Process
- **Three main phases**:  
  1. **Identification** – recognize incidents with SIEM/SOAR alerts.  
  2. **Control** – limit damage, coordinate, communicate, restore operations.  
  3. **Iteration & Improvement** – learn from incidents, update processes, prevent recurrence.  
- **Tools**:  
  - **SOAR** – automation, orchestration, and coordination.  
  - **SIEM** – log collection and analysis.  

---

## Incident Identification
- Triage & prioritize alerts by **severity, impact, urgency**.  
- Collect **logs, traffic, user activity** → assess scope & impact.  
- Differentiate **true incidents vs. false positives** with:  
  - **Analysis** – patterns, evidence, correlations.  
  - **Verification** – confirm compromise through system checks.  

---

## Coordination & Communication
- Success relies on **clear roles**:  
  - Incident Manager  
  - Lead Investigator  
  - Communication Lead  
  - Technical Specialists  
- **Must-have tasks**:  
  - Set goals and objectives.  
  - Define responsibilities.  
  - Establish communication channels.  
  - Track progress.  
  - Keep stakeholders informed.  
- **High-quality communication**: use standardized terms, give regular updates, and use secure channels.  

---

## Documentation Fundamentals
- **Types**: Incident reports, Evidence logs, Action plans, Playbooks, Logbooks.  
- **Qualities**: Accurate, clear, consistent, timely.  
- **Purposes**:  
  - Preserve evidence (file integrity, chain of custody).  
  - Support legal investigations.  
  - Improve organizational learning.  
- **Google Cloud tools**: BigQuery, Chronicle SIEM → secure evidence preservation.  

---

## Documentation Elements
- **Incident summary** – overview, severity, context.  
- **Timeline** – chronological order of events.  
- **Technical findings** – logs, misconfigurations, indicators of compromise.  
- **Actions taken** – mitigation steps.  
- **Lessons learned** – what worked, what failed.  
- **Recommendations** – improvements for the future.  

---

## Playbooks & SOAR
- **Playbook**: reusable workflows (manual or automated).  
- **Structure**: Trigger → Action → Flow.  
- **Benefits**:  
  - Save time, ensure consistency.  
  - Reduce risk, improve collaboration.  
  - Support compliance.  
- **Best practices**: clarity, modularity, regular updates, reusability, and frequent testing.  

---

## Automation vs. Orchestration
- **Automation**: task automation within a single system.  
- **Orchestration**: coordination across multiple systems/platforms.  
- **Key point**: automation feeds into orchestration → they are interdependent.  

---

## Incident Response Partners
- **Chronicle SIEM/SOAR** – log ingestion, ML-based detection, automated playbooks.  
- **Mandiant** – breach analytics, threat hunting, managed defense, enriched threat intelligence.  
- **VirusTotal** – malware and IOC enrichment for detection & triage.  
- **MITRE ATT&CK** – framework of attacker tactics and techniques.  

---

## Logs, Queries, and BigQuery
- **Cloud Audit Logs** – track administrative activity (who, when, where).  
- **Log sinks** – export logs (e.g., to BigQuery).  
- **BigQuery** – large-scale log analysis using SQL.  
- **Example use**: detect VM deletions within the last 7 days.  

---

## Evidence Preservation
- **Documentation**: include summary, timeline, actions, lessons.  
- **Chain of custody**: preserve integrity, timeline, and ownership of evidence.  
- **Prompt evidence collection**: cloud resources may be **ephemeral** or autoscaled.  
- **Security practices**: encryption, access management, and secure storage.  
- **Prioritization**: assess severity, impact, urgency.  
- **Iteration**: refine practices based on past incidents.  

---

## Terms & Definitions
- **Chain of custody**: Documenting and preserving evidence while maintaining its integrity and a clear handling timeline.  
- **Incident**: A violation or imminent threat of violation of security policies or practices.  
- **Playbook**: A manual outlining operational actions and procedures.  
- **SIEM (Security Information and Event Management)**: Collects and analyzes log data to monitor critical activities.  
- **SOAR (Security Orchestration, Automation, and Response)**: A suite of applications, tools, and workflows that automate and coordinate responses to security events.  
