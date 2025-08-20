# Access a firewall and create a rule

---

## Project Objective  
- To **analyze and control inbound network traffic** to a cloud-hosted web server.  
- To **implement firewall rules** that selectively allow or deny access based on port numbers and protocols.  
- To **generate and monitor network traffic logs** for security validation.  
- To **gain practical experience** in applying perimeter protection within a cloud security model.  

---

## Activity Overview  
- **Goal:** Protect a cloud-based web server by controlling inbound traffic.  
- **Why it matters:** Firewalls are critical for preventing unauthorized access, enforcing security policies, and ensuring safe network communication.  
- **How:** By creating, testing, and analyzing firewall rules in Google Cloud.  

---

## Scenario  
- The organization: **Cymbal Bank**  
- The resource: A demo **web server** running on a Virtual Private Cloud (VPC).  
- The concern: The server might be exposed to unnecessary or insecure traffic.  
- The task: Analyze inbound traffic, allow necessary connections, and then block unwanted ones.  

---

## Setup  
- **VPC:** `vpc-net`  
- **Subnet:** `vpc-subnet`  
- **VM Instance:** `web-server` with Apache installed  
- **Tag:** `http-server`  
- **Logs enabled:** VPC Flow Logs  

This environment allowed me to test both permitted and denied traffic scenarios.  

---

## Task 1: Create a Firewall Rule (Allow HTTP + SSH)  
- Created rule: **allow-http-ssh**  
- **Details:**  
  - Network: `vpc-net`  
  - Target: VMs tagged with `http-server`  
  - Source range: `0.0.0.0/0` (all IPv4 addresses)  
  - Allowed ports: **80 (HTTP), 22 (SSH)**  

**Result:** The server was now reachable via browser (HTTP) and via SSH for administrative access.  

![Firewall Rule Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-01.jpg?raw=true)

![Firewall Rule Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-02.jpg)

![Firewall Rule Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-03.jpg)

![Firewall Rule Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-04.jpg)

---

## Task 2: Generate HTTP Traffic  
- Accessed the web server using its **External IP**.  
- Confirmed it displayed the Apache default page.  
- Captured my **client IP address** to later trace logs.  

![Firewall Rule Creation](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-05.jpg)

---

## Task 3: Analyze Flow Logs  
- Used **Logs Explorer** in Google Cloud.  
- Queried logs with my client IP.  
- Observed details:  
  - **dest_ip:** `10.1.3.2` (server’s internal IP)  
  - **dest_port:** 80 (HTTP)  
  - **protocol:** TCP (6)  
  - **src_ip:** my computer’s IP  

Confirmed that traffic was allowed due to the **allow-http-ssh** firewall rule.  

![Firewall Rule Analyze](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-06.jpg)

![Firewall Rule Analyze](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-07.jpg)

---

## Task 4: Create a Firewall Rule to Deny HTTP  
- Created rule: **deny-http**  
- **Details:**  
  - Network: `vpc-net`  
  - Target: `http-server`  
  - Action: **Deny**  
  - Source range: `0.0.0.0/0`  
  - Blocked port: **80 (HTTP)**  

**Result:** HTTP requests to the web server were **blocked**.    
---

![Firewall Rule Deny](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Access%20a%20firewall%20and%20create%20a%20rule-09.jpg) 
---

## Task 5: Analyze Firewall Logs  
- Tried to reconnect to the web server → received an error page.  
- Checked firewall logs:  
  - **dest_ip:** `10.1.3.2`  
  - **dest_port:** 80  
  - **src_ip:** my computer  
  - **disposition:** **DENIED**  
  - **rule applied:** `deny-http`  

Verified that the deny rule was triggered successfully.  

---

## Conclusion  
- Gained **practical experience** in creating and testing firewall rules.  
- Learned how to use **VPC Flow Logs** and **Firewall Logs** to analyze network activity.  
- Understood how **perimeter protection** helps secure cloud workloads.  

This project strengthened my knowledge of **cloud security fundamentals**, especially around controlling inbound and outbound network traffic.  

---

## Key Takeaways  
1. Always **allow only necessary ports** (e.g., HTTP, SSH).  
2. Use **tags** to simplify firewall management.  
3. Monitor with **Flow Logs & Firewall Logs** to verify traffic rules.  
4. Defense in depth starts with **perimeter protection** like firewalls.  

---

