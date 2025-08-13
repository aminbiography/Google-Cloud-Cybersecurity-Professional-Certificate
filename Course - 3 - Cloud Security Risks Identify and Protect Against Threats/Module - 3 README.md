# Cloud-Native Security & Container Management

## Orchestration in Cloud Security
- **Definition & Purpose:** Orchestration automates deployment, scaling, load balancing, networking, provisioning, and lifecycle management for containers.  
- **Declarative Programming:** Used to define the desired state of infrastructure rather than the steps to achieve it.  
- **Key Platforms:** Kubernetes is a popular orchestration platform, managing clusters, nodes, and pods.  
- **Scaling:** Horizontal pod autoscaling and virtual autoscaling adjust resources based on demand.  
- **Security Integration:** Orchestration can halt deployments when policy violations (e.g., vulnerabilities) are detected.  
- **RBAC in Kubernetes:** Ensures least privilege access by assigning roles to users or service accounts.

---

## Container Security Best Practices
- **Trusted Images:** Always use images from verified registries to prevent malicious or tampered code.  
- **Vulnerability Scanning:** Regular scans and timely patching are critical, especially for kernel-level issues.  
- **RBAC Implementation:** Restrict service account permissions to limit potential privilege escalation.  
- **Separate Service Accounts:** Assign different accounts for different workloads to minimize cross-environment risks.  
- **Container Drift Prevention:** Make containers immutable to prevent unauthorized changes after deployment.

---

## Cloud-Native Design & Security Concepts
- **Cloud-Native Design:** Creating applications optimized for cloud environments with scalability, flexibility, and automation.  
- **Ephemerality & Immutability:** Resources should be short-lived and unchangeable after deployment to enhance security.  
- **Infrastructure as Code (IaC) & Policy as Code (PaC):** Automating infrastructure and security policy management using reusable scripts.  
- **Shared Responsibility Model:** Security responsibilities are divided between the cloud provider and the customer.

---

## Key Tools & Technologies
- **Kubernetes Components:**  
  - **Nodes:** Machines running containers.  
  - **Pods:** Groups of one or more containers with shared resources.  
  - **Clusters:** Collections of pods and nodes managed as a unit.  
- **Terraform Workflow:** Write IaC → Plan → Apply → Review.  
- **Docker:** A platform for building, running, and managing containers.

---

## Risk Management & Security Policies
- **Policy Updates:** Continuous updates align security measures with evolving technology and threats.  
- **Versioning Policies:** Retaining old versions provides rollback capability if new policies cause issues.  
- **Role of Automation:** Automates testing, orchestration, configuration management, and security enforcement.

---

## Key Takeaways
- **Group and isolate services** using namespaces.  
- **Make containers immutable** to prevent drift.  
- **Use declarative programming** for orchestration.  
- **Relocate containers** to other hosts during outages.  
- **Patch kernel-level vulnerabilities** to avoid privilege escalation.  
- **Implement RBAC and least privilege** for service accounts.  
- **Rely on CSPs** to maintain physical servers and hardware.  
- **Update the host kernel** to safeguard against exploits.

