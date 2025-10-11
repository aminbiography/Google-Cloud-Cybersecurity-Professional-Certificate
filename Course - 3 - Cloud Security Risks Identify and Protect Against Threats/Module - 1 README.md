# Cloud Security and Access Control

## Cloud Security Foundations

- **Perimeter Protection**: Involves using tools like firewalls, IDS, IPS, and physical controls to guard the outer boundaries of a network.
- **Zero Trust Model**: Based on the principle **"never trust, always verify"**, requiring explicit authentication and authorization for all access, regardless of location.
- **Trust Boundaries**: Defined zones of different access levels; important for separating trusted internal systems from untrusted external sources.

---

## Identity and Access Management (IAM)

- **Authentication**: Verifies user identity (e.g., username/password, MFA).
- **Authorization**: Grants access to specific resources based on identity or role.
- **IAM Services**: Central to managing digital identities, often paired with SSO and MFA for robust access management.
- **SSO (Single Sign-On)**: Allows users to log in once and gain access to multiple systems.
- **MFA (Multi-Factor Authentication)**: Requires two or more verification methods to enhance security.

---

## Access Control Models

- **RBAC (Role-Based Access Control)**: Grants access based on user roles.
- **ABAC (Attribute-Based Access Control)**: Uses user, resource, and environmental attributes to control access.
- **DAC (Discretionary Access Control)**: Data owners manage who has access.
- **MAC (Mandatory Access Control)**: Access is governed by strict policies, often used in high-security environments.

| Model    | Description                                                                           |
| -------- | ------------------------------------------------------------------------------------- |
| **RBAC** | Role-Based Access Control – Access based on user roles.                               |
| **ABAC** | Attribute-Based Access Control – Access based on user/resource attributes.            |
| **DAC**  | Discretionary Access Control – Data owner grants/revokes access.                      |
| **MAC**  | Mandatory Access Control – Strict policy-based access (often in secure environments). |

---

## Firewall Configuration in Google Cloud

- **Firewall Rules**: Control traffic to/from VM instances. Settings include:
  - Direction (Ingress/Egress)
  - Action (Allow/Deny)
  - Source/Destination IP ranges
  - Protocols/Ports (e.g., TCP 80 for HTTP)
- **VPC Flow Logs**: Capture and analyze traffic data for monitoring and auditing.
- **Firewall Rule Logging**: Logs whether a rule allowed or denied specific connections.
- **Use of Tags**: Target tags help apply rules to specific VMs.

---

## Attack Vectors & Threat Management

- **Common Attack Vectors**:
  - **Password Attacks**: Often use brute force.
  - **Phishing/Vishing/Smishing**: Social engineering techniques.
  - **Malware**: Harmful software intended to damage systems.
  - **DDoS**: Floods a system with traffic from multiple sources.
- **Mitigation Strategies**:
  - MFA, user training, strong password policies.
  - Software patching and vulnerability scans.
  - DDoS protection tools and traffic monitoring.

---

## Zero Trust Components

- **Core Principles**:
  - **Verify Explicitly**: Every access request must be authenticated.
  - **Least Privilege Access**: Only give users what they need.
  - **Assume Breach**: Operate as if systems are already compromised.
- **Security Mechanisms**:
  - **Micro-Segmentation**: Isolates network areas to contain breaches.
  - **Network Access Control (NAC)**: Enforces policy-based device/user access.
  - **CASBs & SASE**: Enforce security policies and provide context-aware access in cloud environments.

---

## Logs Explorer and Auditing

- **Logs Explorer in Google Cloud**:
  - Query builder for log filtering and analysis.
  - Can track connections, rule enforcement, or deny actions.
- **Auditing**:
  - Ensures security policies are followed.
  - Identifies potential breaches and improves compliance.

---

## ACLs and Fine-Grained Access

- **Access Control Lists (ACLs)**: Grant permissions (e.g., read/write) to specific users/groups on individual cloud resources like storage buckets.
- **Used with IAM**: ACLs complement IAM by offering fine-tuned control over object-level access.

---

# Key Cloud Security Concepts (Remainder)

## Authentication vs. Authorization

- **Authentication**: Proves a user's identity (e.g., via password, MFA).
- **Authorization**: Grants access to specific resources based on verified identity.

---

## Zero Trust Principles

1. **Verify Explicitly**  
   Authenticate and authorize every request.

2. **Apply Least Privilege**  
   Grant only the minimum access necessary.

3. **Assume Breach**  
   Design as if the system is already compromised.

---

## IAM Importance

- Provides **centralized identity and policy management**
- Supports role-based and attribute-based access
- Integrates with tools like SSO and MFA for enhanced security

---

## OpenID

- Enables **single sign-on** (SSO) functionality
- **Reduces password fatigue**
- **Prevents credential reuse** across platforms

---

## Security Audit

- **Identifies vulnerabilities** in the system
- **Recommends improvements** to strengthen security posture

