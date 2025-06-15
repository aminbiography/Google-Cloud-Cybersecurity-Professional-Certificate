# Cloud Security & DevSecOps For Cloud Computing 

## DevSecOps & Software Pipelines
- **DevSecOps** integrates development, security, and operations to enhance collaboration and automate security across the software development lifecycle.
- **Software pipelines** automate CI/CD (Continuous Integration and Continuous Delivery/Deployment) for efficient code builds, testing, and releases.
- **CI** integrates code changes into a shared repository.
- **CD** either delivers builds to staging (delivery) or deploys them to production (deployment).

## Security Best Practices
- **Shift Left**: Integrate security early and throughout development.
- **IAM**: Apply Identity and Access Management to control access.
- **Security Hardening**: Reduce attack surfaces through configuration and automation.
- **SBOM (Software Bill of Materials)**: Lists components to track vulnerabilities and ensure compliance.

## Infrastructure as Code (IaC)
- IaC automates infrastructure provisioning using code (e.g., Terraform).
- **Declarative approach**: Define the system’s desired state; tools enforce it automatically.
- Benefits:
  - Reduces **configuration drift**.
  - Improves **visibility**, **version control**, and **collaboration**.
  - Lowers **human error** risk and operational costs.

## Policy as Code (PaC)
- Use code to define and automate policies and compliance rules.
- Supports **automated alerts**, **version control**, and **collaboration**.
- Ensures **continuous compliance** with frameworks like HIPAA or PCI.

## GitOps
- GitOps applies Git-based workflows to manage infrastructure.
- Uses **pull requests**, **commits**, and **branches** as the single source of truth.
- Benefits:
  - Unified management of apps & infra.
  - Supports **CI/CD**, visibility, and **shift-left** security.
  - Ideal for **containerized** environments (e.g., Kubernetes).

## Terraform (IaC Tool)
- Open-source, cloud-agnostic tool for provisioning cloud infrastructure.
- Defines **resources** using `.tf` config files.
- Resource blocks (e.g., VPC, subnetwork, VM) specify type, location, and parameters.
- Helps eliminate **manual misconfiguration** and drift.

## Summary Points 
- Understand **CI/CD**, **DevSecOps culture**, and **IaC/PAC/GitOps** roles in security automation.
- Know how to reduce **human error**, prevent **drift**, and ensure **traceability** using tools like **Terraform** and practices like **version control**.
- Be ready to explain **SLSA levels**, **SBOMs**, and how they secure the **software supply chain**.

---
