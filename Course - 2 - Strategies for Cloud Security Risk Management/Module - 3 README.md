# Cloud Security Compliance and Policy Enforcement

---

## Key Topics

### Policy as Code (PaC)
- Automates and enforces security rules using code (e.g., Python, YAML, Rego).
- Enhances **collaboration**, **efficiency**, **visibility**, and **version control**.
- Language choice depends on the enforcement tools (e.g., Terraform, Chef).

### Compliance & Non-Compliance
- **Compliance**: Adherence to legal, regulatory, and organizational standards.
- **Non-compliance**: Results in reputational loss, fines, legal action, and loss of trust.
- Examples: HIPAA and PCI DSS obligations for healthcare and payment data.

### Cloud Resource Hierarchy & Controls
- **Hierarchy levels**: Organization > Folder > Project.
- Set policies at the **appropriate level** to ensure effective scope and inheritance.
- Use **security guardrails** to prevent insecure actions automatically.

### Cloud Audit & Assessment
- **Audit preparation steps**:
  1. Study audit requirements.
  2. Identify asset and control inventory.
  3. Conduct a gap assessment.
  4. Perform internal test audits.
- **Benefits of audits**:
  - Build trust
  - Identify vulnerabilities
  - Improve compliance readiness

### Compliance Lifecycle
- Lifecycle Steps:
  1. Control Mapping
  2. Gap Assessment
  3. Implement Controls
  4. Monitor & Maintain
- Purpose: Ensure alignment with **regulations** and **business goals**.

### Types of Security Controls
- **Preventative**: Stop incidents before they happen.
- **Detective**: Identify and log security incidents.
- **Corrective**: Respond and recover after an incident.
- **Deterrent**: Discourage potential attackers.
- **Compensating**: Fill gaps where standard controls are not feasible.

### Control Mapping & Inventory
- Map controls to frameworks like NIST SP 800-53.
- Use tools like spreadsheets to track:
  - Control title
  - Domain
  - Asset group
  - Compliance status

---

## Sample Use Cases & Scenarios
- Creating secure password and passphrase policies.
- Applying multi-factor authentication (MFA).
- Aligning cloud policies to HIPAA/PCI compliance using inherited controls.
- Configuring auto-lock policies on endpoints to reduce insider threats.

---

## Tools & Best Practices
- Infrastructure as Code (IaC) and Policy as Code (PaC).
- Use **audit logs**, **threat intelligence feeds**, and **simulation training**.
- Automate testing and deployment with **dry-run modes** before production rollout.

---

## Final Takeaways
- Cloud security isn’t just technical—it’s also **regulatory**, **procedural**, and **strategic**.
- Strong governance, continuous improvement, and automated controls are key to success.
- Understanding frameworks like **NIST SP 800-53**, **HIPAA**, and **PCI DSS** gives you an edge in both audits and real-world security operations.

