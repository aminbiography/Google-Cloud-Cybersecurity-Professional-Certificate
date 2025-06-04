# Security Principles in Cloud Computing

---

## Core Cloud Concepts

- **Cloud Computing**: Delivery of computing services (compute, storage, networking) over the internet.
- **On-Premises vs. Cloud**: On-premises means locally managed infrastructure; cloud services are managed by a **Cloud Service Provider (CSP)**.
- **Scalability**: Ability to increase or decrease resources as needed.
- **Latency**: Time it takes for data to travel between locations.
- **Ephemerality**: Cloud resources can be short-lived and quickly replaced, enhancing flexibility and security.

---

## Cloud Models

- **Public Cloud**: Shared infrastructure delivered over the internet.
- **Private Cloud**: Dedicated to one organization, often on-premises.
- **Hybrid Cloud**: Combination of public and private environments.
- **Multicloud**: Use of multiple cloud service providers.

---

## Compute, Storage, and Networking

- **Compute**: Processing power delivered via virtual machines or containers.
- **Instance**: A virtual server used to run workloads in the cloud.

### Storage Types

- **File Storage**: Hierarchical structure of files and folders.
- **Block Storage**: Splits data into blocks stored separately for efficiency.
- **Object Storage**: Stores unstructured data in "buckets".
- **Structured Data**: Organized (e.g., rows and columns).
- **Unstructured Data**: Includes images, audio, documents, etc.

---

## Google Cloud Storage Classes

- **Standard**: For frequently accessed (hot) data.
- **Nearline**: Accessed approximately monthly.
- **Coldline**: Accessed approximately quarterly.
- **Archival**: Accessed rarely (e.g., annually).

---

## Redundancy & Resiliency

- **Redundancy**: Replicating data across regions/zones to prevent data loss.
- **Failure Domain**: A segment of infrastructure that can fail without disrupting service.
- **Zone/Region**: Logical groupings of data centers.

---

## Cloud Security Essentials

- **Confidentiality, Integrity, Availability (CIA Triad)**: Core security principles.
- **Shared Responsibility Model**: CSP secures infrastructure; user secures data/functions.
- **Immutability**: Resources can't be altered after creation, reducing configuration drift.

---

## Containers & Virtualization

- **Containers**: Lightweight software packages with all needed code and dependencies.  
  **Benefits**: Portability, Immutability, Responsibility Separation.
- **Virtualization**: Creating virtual versions of hardware via hypervisors:
  - **Type 1 Hypervisor**: Runs directly on hardware (bare metal).
  - **Type 2 Hypervisor**: Runs on an existing OS (hosted).

---

## Serverless Computing

- **Serverless**: Developers write code; CSP handles infrastructure.
- **BaaS (Backend as a Service)**: CSP manages entire backend.
- **FaaS (Function as a Service)**: Executes short-lived functions in response to events.

**Benefits**: Scalability, cost-efficiency, faster development.

---

## Repositories & Development

- **Repository**: Central storage for code/data sharing and collaboration.
- **Testing Environments**: Easily created with virtual machines or containers for safe testing.

---

