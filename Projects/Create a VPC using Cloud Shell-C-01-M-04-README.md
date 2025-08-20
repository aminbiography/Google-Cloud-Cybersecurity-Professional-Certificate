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
- **Approach:** Replicate the planned setup by creating a test VPC and subnet in Google Cloud.  

---

## Setup  
- **Tool:** **Cloud Shell** (with `gcloud` CLI pre-installed).  

---

## Task 1: Create a Custom VPC Network  
- Run the following command in Cloud Shell:  
  ```bash
  gcloud compute networks create labnet --subnet-mode=custom
  ```
- **Result:** A custom mode VPC named `labnet` was created.  
- **Verification:**  
  - Subnet mode: **CUSTOM**  
  - BGP Routing: **REGIONAL**  

---

## Task 2: Create a Subnet  
- Run the following command in Cloud Shell:  
  ```bash
  gcloud compute networks subnets create labnet-sub \
     --network labnet \
     --region us-east4 \
     --range 10.0.0.0/28
  ```
- **Result:** Subnet `labnet-sub` was created in region `us-east4`.  

---

## Task 3: View Networks  
- Run:  
  ```bash
  gcloud compute networks list
  ```
- **Output:**  
  - `default` network (auto-created by GCP).  
  - `labnet` network (created in Task 1).  
- **Answer Check:** Subnet mode of `labnet` → **CUSTOM**  

---

## Task 4: List Subnets  
- Run:  
  ```bash
  gcloud compute networks subnets list --network=labnet
  ```
- **Output:**  
  - Subnet name: `labnet-sub`  
- **Answer Check:** Subnet name in `labnet` → **labnet-sub**  

---

## Conclusion  
- Successfully created a **custom VPC network** (`labnet`) and a **subnet** (`labnet-sub`).  
- Learned how to:  
  1. Create networks and subnets using Cloud Shell.  
  2. Verify network configurations with `gcloud` commands.  
  3. Prepare test environments for **hybrid cloud migration security testing**.  

This hands-on exercise provided practical experience in **cloud networking fundamentals** and reinforced the importance of **isolated test environments** before deploying security policies in production.  

---

## Key Takeaways  
1. Use **custom VPCs** for more control over subnet configurations.  
2. Always **verify created networks and subnets** using `gcloud` commands.  
3. Segmentation with **subnets** improves security, performance, and organization.  
4. Test environments are critical for **validating network security** before production rollout.  

