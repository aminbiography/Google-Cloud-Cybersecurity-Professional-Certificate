# **Project Title:** **Respond and Recover from a Data Breach in Google Cloud**

---

## **Project Scenario:**

Cymbal Retail, a multinational retail company with both online and physical operations, recently experienced a significant data breach that exposed sensitive customer information. As a Cloud Security Associate, my role is to assist the security team in identifying the vulnerabilities that caused the breach, containing the threat, recovering compromised resources, and verifying PCI DSS compliance using Google Cloud Security Command Center (SCC).

---

## **Project Objective:**

To identify, remediate, and verify the resolution of cloud security vulnerabilities in Google Cloud following a simulated data breach. The project demonstrates key cybersecurity capabilities, including vulnerability assessment, incident response, and compliance verification.

---

## **Project Steps (Description):**

---

### **1. Analyze the Data Breach and Gather Information**

1. In the **Navigation menu**, click **Security → Security Command Center**.
2. Review the **Risk Overview** page to identify current vulnerabilities.
3. Scroll down to **Active vulnerabilities** and open the **Findings by Resource Type** tab.
4. Identify which resource types show **high-severity** findings (Compute Instances, Buckets, Firewall).
5. Then, go to **Compliance → PCI DSS 3.2.1 → View details** and sort findings by **Active** to identify compliance gaps.

**Image 01:** Risk Overview Dashboard  

![Risk Overview Dashboard](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-01.jpeg)

**Image 02:** Misconfiguration Findings by Resource Type

![Misconfiguration Findings by Resource Type](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-02.jpeg)

**Image 03:** PCI DSS 3.2.1 Compliance Results

![PCI DSS 3.2.1 Compliance Results](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-03.jpeg)

---

### **2. Fix Compute Engine Vulnerabilities**

1. In the **Navigation menu**, go to **Compute Engine → VM Instances**.
2. Select the compromised VM `cc-app-01` and click **Stop**. Confirm the stop action.
3. Click **Create Instance**, name it `cc-app-02`, and under **Boot Disk**, choose **Snapshots → cc-app01-snapshot**.
4. Set **Machine type:** e2-medium, **Region:** `us-west1-c`, and **Network tags:** cc.
5. Under **Networking**, remove the **External IP** (set to None).
6. Under **Security**, select **Turn on Secure Boot**.
7. Assign the **Qwiklabs User Service Account** under Identity and API access.
8. Click **Create** to deploy the clean VM.

**Image 04:** Firewall Rule Findings (Open SSH/RDP Ports)

![Firewall Rule Findings (Open SSH/RDP Ports)](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-04.jpeg)

**Image 05:** Stopping the Compromised VM (cc-app-01)

![Stopping the Compromised VM (cc-app-01)](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-05.jpeg)

**Image 06:** Creating a New VM from Snapshot in Region `us-west1-c`

![Creating a New VM from Snapshot in Region](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-06.jpeg)

**Image 07:** New VM Instance (cc-app-02) Running in `us-west1-c`

![New VM Instance (cc-app-02) Running in](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-07.jpeg)

---

### **3. Fix Cloud Storage Bucket Permissions**

1. Go to **Cloud Storage → Buckets**.
2. Click the project bucket name (for example, `qwiklabs-gcp-XXXX-bucket`).
3. Under the **Permissions** tab, locate **Public access** and click **Prevent public access** → Confirm.
4. Enable **Uniform Bucket-Level Access (UBLA)**.
5. Remove **allUsers** and **allAuthenticatedUsers** permissions from the list.
6. Verify the bucket is no longer publicly accessible.

**Image 08:** Cloud Storage Bucket Settings

![Cloud Storage Bucket Settings](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-08.jpeg)

---

### **4. Limit Firewall Ports Access**

1. Navigate to **VPC Network → Firewall**.
2. Click **Create firewall rule** and enter:

   * **Name:** `limit-ports`
   * **Targets:** Specified target tags → `cc`
   * **Source IP ranges:** `35.235.240.0/20` (Google IAP range)
   * **Protocols and ports:** TCP:22
3. Click **Create**.
4. Verify that SSH access is now limited to only Google IAP addresses.

---

### **5. Fix the Firewall Configuration**

1. Go to **VPC Network → Firewall**.
2. Delete the following default rules:

   * `default-allow-icmp`
   * `default-allow-rdp`
   * `default-allow-ssh`
3. Locate the rules `limit-ports` and `default-allow-internal`.
4. Click **Edit** on each and enable **Logging → On**.
5. Save the changes.
6. Verify that both rules now have logging enabled.

**Image 09:** Firewall Configuration Review

![Firewall Configuration Review](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-09.jpeg)

**Image 10:** Final Firewall Policies with Logging On

![Final Firewall Policies with Logging On](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-10.jpeg)

---

### **6. Verify Compliance**

1. In the **Security Command Center**, click **Compliance**.
2. Under **Google Cloud compliance standards**, open the **PCI DSS 3.2.1** tile.
3. Click the **Findings** column to display active findings first.
4. Verify that all **high** and **medium** findings are resolved.
5. Confirm that only low-severity findings (e.g., VPC Flow Logs disabled) remain.

**Image 11:** Final Compliance Verification – High and Medium Findings Resolved

![inal Compliance Verification](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Respond%20and%20recover%20from%20a%20data%20breach-11.jpeg)

---

## **Project Conclusion:**

By completing this project, I successfully identified and remediated the vulnerabilities that contributed to a simulated data breach in a Google Cloud environment. I restored compromised resources, secured Cloud Storage, hardened firewall configurations, and validated compliance. This project demonstrates foundational skills in **cloud incident response**, **vulnerability management**, and **compliance verification**.

---

## **Project Credit:**

- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.

---

