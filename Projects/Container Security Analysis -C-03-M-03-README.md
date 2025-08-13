# Container Security Analysis – Cymbal Bank

## Objective
To assess the security of a staging environment container and provide actionable recommendations for securing containers in Cymbal Bank’s development lifecycle.

---

## Current Configuration
**Container Details:**
- **Image Source:** Pulled from an **official and trusted registry**.
- **Security Scan Result:** **Kernel-level vulnerability** detected.
- **Kubernetes Service Account:** One account with **unrestricted access** shared by all developers.

**Diagram Overview:**
- Container connected to the **Internet**.
- Vulnerability present in the container.
- Kubernetes service account has **admin-level privileges**.

---

**Configuration Diagram:**

![Container Configuration]()

---

## Security Risks Identified
1. **Kernel-Level Vulnerability**  
   - High-risk exposure if exploited.  
   - Could allow privilege escalation or compromise the host environment.

2. **Overprivileged Service Account**  
   - Violates the **principle of least privilege**.  
   - Increases potential damage if credentials are compromised.

3. **Shared Credentials**  
   - All developers using the same account.  
   - Reduces accountability and increases insider threat risk.

---

## Security Recommendations – Checklist

| # | Best Practice | Explanation | Status |
|---|---------------|-------------|--------|
| 1 | **Use verified and trusted container images** | Already implemented. The container image is pulled from an official, trusted registry. | ✅ |
| 2 | **Perform vulnerability scanning and timely patching** | Vulnerability scan revealed a kernel-level flaw. Update to a patched image version to mitigate risk. | ❌ |
| 3 | **Implement Role-Based Access Control (RBAC)** | Current service account has unrestricted access. Apply RBAC to grant minimal required permissions. | ❌ |
| 4 | **Use separate service accounts for different workloads** | All developers share the same account. Assign distinct accounts with scoped permissions to improve security and traceability. | ❌ |

---

## Proposed Container Security Lifecycle
1. **Image Acquisition** – Only from **trusted registries**.  
2. **Vulnerability Management** – Regular scans & immediate patching of critical issues.  
3. **Access Control** – RBAC for **least privilege**.  
4. **Service Account Management** – Segregation by application/team.  
5. **Continuous Monitoring** – Implement container runtime security tools.

---

## Conclusion
While Cymbal Bank has taken the first step by using a trusted image source, critical improvements are needed in **patch management** and **access control** before deploying to production. Addressing these issues will significantly reduce the attack surface and improve the resilience of the bank’s containerized applications.
