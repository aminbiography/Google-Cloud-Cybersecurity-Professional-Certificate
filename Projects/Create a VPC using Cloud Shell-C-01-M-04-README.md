# Create a VPC using Cloud Shell  

---

## Project Objective  
- To **learn how to create a Virtual Private Cloud (VPC)** and subnets using Google Cloud Shell.  
- To **practice network segmentation** in a test environment before moving to production.  
- To **gain hands-on experience** with the `gcloud` CLI for cloud networking.  
- To **prepare for securing hybrid cloud environments** in a financial institution setup.  

---

## Activity Overview  
- **Goal:** Build and manage a custom VPC network with subnets.  
- **Why it matters:** VPCs provide isolation, segmentation, and security for workloads in the cloud.  
- **How:** By creating a network, adding subnets, and validating configurations using Cloud Shell.  

---

## Scenario  
- **Organization:** **Cymbal Bank**  
- **Context:** Migration from on-premises to hybrid cloud.  
- **Task:** As a junior cloud security analyst, you must test and validate the security of newly architected network infrastructure.  
- **Approach:** Replicate the planned setup by creating a test VPC and subnet in Google Cloud.  

---

## Setup  
- **Tool:** **Cloud Shell** (with `gcloud` CLI pre-installed).  
- **Resources Provided:**  
  - Preconfigured GCP project with default VPC  

---

## Task 1: Authenticate and Configure Project  
- Checked active account and project configuration:  
  ```bash
  gcloud auth list
  gcloud config list project
  ```
- **Result:** Confirmed student account and project ID.  

![Auth and Project Config](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-01.png)  


![Project Config](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-02.png)  

---

## Task 2: Create a Custom VPC Network  
- Run the following command in Cloud Shell:  
  ```bash
  gcloud compute networks create labnet --subnet-mode=custom
  ```
- **Result:** A custom mode VPC named `labnet` was created.  
- **Verification:**  
  - Subnet mode: **CUSTOM**  
  - BGP Routing: **REGIONAL**  

![Create VPC](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-03.png)  

---

## Task 3: Create a Subnet  
- Run the following command in Cloud Shell:  
  ```bash
  gcloud compute networks subnets create labnet-sub \
     --network labnet \
     --region us-east4 \
     --range 10.0.0.0/28
  ```
- **Result:** Subnet `labnet-sub` was created in region `us-east4`.  

![Subnet Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-04.png)  

---

## Task 4: View Networks  
- Run:  
  ```bash
  gcloud compute networks list
  ```
- **Output:**  
  - `default` network (auto-created by GCP).  
  - `labnet` network (created in Task 2).  
- **Answer Check:** Subnet mode of `labnet` → **CUSTOM**  

![View Networks](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-05.png)  

---

## Task 5: List Subnets  
- Run:  
  ```bash
  gcloud compute networks subnets list --network=labnet
  ```
- **Output:**  
  - Subnet name: `labnet-sub`  
- **Answer Check:** Subnet name in `labnet` → **labnet-sub**  

![List Subnets](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-06.png)  

---

## Extra: Firewall Setup Prompt  
- GCP suggests creating firewall rules to allow necessary inbound traffic.  
- Example:  
  ```bash
  gcloud compute firewall-rules create allow-internal --network labnet --allow tcp,udp,icmp --source-ranges <IP_RANGE>
  ```

![Firewall Setup](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Create%20a%20VPC%20using%20Cloud%20Shell-07.png)  

---

## Conclusion  
- Successfully created a **custom VPC network** (`labnet`) and a **subnet** (`labnet-sub`).  
- Learned how to:  
  1. Authenticate and configure project access.  
  2. Create networks and subnets using Cloud Shell.  
  3. Verify network configurations with `gcloud` commands.  
  4. Prepare test environments for **hybrid cloud migration security testing**.  

This hands-on exercise provided practical experience in **cloud networking fundamentals** and reinforced the importance of **isolated test environments** before deploying security policies in production.  

---

## Key Takeaways  
1. Use **custom VPCs** for more control over subnet configurations.  
2. Always **verify created networks and subnets** using `gcloud` commands.  
3. Segmentation with **subnets** improves security, performance, and organization.  
4. Test environments are critical for **validating network security** before production rollout.

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  

---
