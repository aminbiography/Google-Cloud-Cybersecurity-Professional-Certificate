# Compliance Report Notes

## Security Controls and Findings

| Security Control        | Severity | Findings                                                  | Recommendations                                                                                                                                                                                                                      |
|-------------------------|----------|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **AC-6: FULL_API_ACCESS** | Medium   | 1 account: `cymbal-apps@appspot.gserviceaccount.com`        | Limit the default service account permissions by assigning only the minimum required roles. Avoid granting full API access to service accounts unless absolutely necessary. Use custom roles to enforce least privilege.             |
| **CA-3 SC-7: PUBLIC_IP_ADDRESS** | High     | 2 virtual machines (VMs): `instance-1`, `instance-2`         | Remove public IP addresses from these VMs. Use private IPs and access them via a bastion host or VPN tunnel. Public-facing services should route through load balancers or secure proxies with appropriate firewall rules.         |
| **IA-2: MFA_NOT_ENFORCED** | High     | 5 user accounts                                             | Enforce multi-factor authentication (MFA) for all users to enhance account security. This greatly reduces the risk of unauthorized access, especially if credentials are compromised. Use identity providers that support MFA.      |
| **AC-3: SQL_NO_ROOT_PASSWORD** | High     | 0 accounts listed, but issue described                      | Ensure all MySQL instances have a strong root password configured. Disable remote root access and enforce strong database authentication policies to prevent unauthorized administrative access.                                      |

---

## Summary of Issues and Recommendations

- **AC-6 (Full API Access):** A service account has overly broad permissions. Reduce its access to the minimum necessary using custom roles.
- **CA-3 SC-7 (Public IP Address):** Two VMs are publicly accessible. Remove public IPs and implement secure, private access methods.
- **IA-2 (MFA Not Enforced):** MFA is not enabled for multiple accounts. Enforce MFA across the organization.
- **AC-3 (SQL No Root Password):** Databases must not allow root access without strong credentials. Apply strong password policies and restrict remote root login.

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Coursera)  
- **Guidance & Framework**: Google Cloud documentation & instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  


