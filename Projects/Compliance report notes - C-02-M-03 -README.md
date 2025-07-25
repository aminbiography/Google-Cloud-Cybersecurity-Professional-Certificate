# Compliance Report Notes

This report documents security control deficiencies identified during a compliance review of the cloud environment. Each issue is categorized by its control reference, assessed severity, and risk impact. The objective is to guide remediation efforts that align with industry best practices and regulatory standards such as NIST, CIS Benchmarks, and organizational policy.

---

## Project Description

The purpose of this project is to assess the current security posture of the cloud infrastructure and identify any gaps in compliance with core access, authentication, and network security controls. By analyzing misconfigured or missing controls, this report aims to provide actionable recommendations that will:

- Strengthen access and identity management
- Reduce unnecessary exposure to public networks
- Enforce least privilege principles
- Improve database security

This documentation supports internal audits, compliance tracking, and prioritization of remediation work.

---

## Findings and Recommendations

| **Security Control**         | **Severity** | **Findings**                                                                                   | **Recommendations**                                                                                                                                             |
|------------------------------|--------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **AC-6: FULL_API_ACCESS**    | Medium       | 1 service account (`cymbal-apps@appspot.gserviceaccount.com`) has full API access.            | Limit the default service account’s permissions. Assign only the minimum required roles. Use **custom roles** following the principle of **least privilege**.   |
| **CA-3 / SC-7: PUBLIC_IP_ADDRESS** | High         | 2 VMs (`instance-1`, `instance-2`) are assigned public IP addresses.                            | Remove public IPs. Use **private IPs** with access via **bastion host** or **VPN tunnel**. Public services should be routed through **load balancers or proxies** with firewall rules. |
| **IA-2: MFA_NOT_ENFORCED**   | High         | 5 user accounts do not have multi-factor authentication (MFA) enabled.                        | Enforce **MFA for all user accounts**. Integrate with identity providers that support MFA across all services to prevent unauthorized access.                    |
| **AC-3: SQL_NO_ROOT_PASSWORD** | High       | No specific account listed, but root access is not properly secured on MySQL instances.       | Ensure **all MySQL instances** have a **strong root password**. Disable remote root login and enforce **strong authentication policies** for database access.     |

---

## Summary of Issues and Recommendations

- **AC-6 (Full API Access):** Restrict service account permissions. Implement least privilege via custom IAM roles.
- **CA-3 / SC-7 (Public IP Address):** Remove public-facing IPs on VMs. Use secure internal network configurations.
- **IA-2 (MFA Not Enforced):** Enforce multi-factor authentication across all user accounts to prevent unauthorized access.
- **AC-3 (SQL No Root Password):** Ensure strong password enforcement and root access control for database instances.

---

## Conclusion

The findings outlined in this report indicate several high-priority risks that must be addressed to maintain a secure and compliant cloud environment. Implementing the recommended security controls will:

- Minimize the attack surface
- Improve identity and access management
- Protect sensitive resources from external threats
- Bring systems in line with compliance frameworks

Ongoing monitoring and periodic audits are essential to ensuring these controls remain enforced and updated as the infrastructure evolves. A follow-up review is recommended post-remediation to verify the effectiveness of the changes.

