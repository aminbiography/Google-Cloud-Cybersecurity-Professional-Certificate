# Cloud Service Models, IAM, and Network Security 

---

## Cloud Service Models

- **IaaS (Infrastructure as a Service)**: CSP manages physical infrastructure; customer manages OS, VMs, data, and security.
- **PaaS (Platform as a Service)**: CSP manages infrastructure and development tools; customer handles application development and data.
- **SaaS (Software as a Service)**: CSP manages the entire stack; customer manages data and access control (e.g., Gmail).
- **FWaaS (Firewall as a Service)**: Cloud-hosted firewalls managed by CSPs to control traffic and protect cloud networks.

---

## Security Responsibility Models

- **Shared Responsibility Model**: Cloud security is shared between the CSP and the customer.
- **Shared Fate Model**: CSP takes a more active role in guiding and securing the customer’s journey across the cloud lifecycle.

---

## Identity and Access Management (IAM)

- **Principals**: Identities like users or services with access rights.
- **Roles**: Collections of permissions assigned to principals.
- **Groups**: Collections of principals for easier role management.
- **Policies**:
  - **Allow Policy**: Grants conditional access to resources.
  - **Deny Policy**: Restricts specific actions from being taken.

**Best Practices**:
- Apply the **Principle of Least Privilege**.
- Enforce **Separation of Duties**.
- Use **Multi-Factor Authentication (MFA)**.
- Use **Federation** for external identities (e.g., "Sign in with Google").

---

## Cloud Networking

- **SDN (Software-Defined Networking)**: Networking devices like routers and switches are managed as virtual services.
- **Load Balancing**:
  - **Application Load Balancer (Layer 7)**: Distributes HTTP/S traffic to multiple servers.
  - **Network Load Balancer (Layer 4)**: Manages TCP/UDP traffic for optimal delivery.
- **VPC (Virtual Private Cloud)**:
  - Isolated cloud environment within the public cloud.
  - Supports **network segmentation** via subnets.
  - Connects to on-prem via **Cloud VPN** or **Cloud Interconnect**.

---

## Firewall and Network Security

- **Cloud Firewalls**: Software-based firewalls managed by CSPs, configured by the customer.
- **FWaaS**:
  - Scales with network demand.
  - Helps protect increased access points in dynamic environments.

**Best Practices**:
- Enforce **least privilege** on all firewall rules.
- Use **hierarchical policies** across org/folder/project levels.
- Choose FWaaS solutions optimized for your CSP (e.g., Google Cloud Firewall).

---

## Additional Cloud Security Concepts

- **Defense in Depth**: Use multiple layers of protection across data, apps, networks, and endpoints.
- **Lift and Shift**: Migrating workloads to the cloud with minimal or no changes.
- **Landing Zone**: Pre-configured environment that provides a secure and scalable starting point in the cloud.
- **API (Application Programming Interface)**: Interfaces that allow apps to communicate with services or systems securely.

---

## Relevant Roles

This knowledge applies to the following roles:

- Cloud Security Engineer  
- Security Analyst  
- DevSecOps Engineer  
- Cloud Architect  
- IAM Specialist  

---

🧠 _Tip: Practice real-world use cases and scenario-based questions to demonstrate your understanding of shared responsibilities, IAM design, VPC setup, and securing cloud workloads._




