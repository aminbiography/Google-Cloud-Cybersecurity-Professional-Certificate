# Risk Management Policy Notes

This document outlines recommended changes to the organization's Risk Management Policy based on NIST 800-53 guidance. Each change addresses identified gaps in policy controls and enhances the organization's overall security posture by aligning with federal compliance standards and industry best practices.

---

## Project Description

The objective of this review is to evaluate the current risk management policy and recommend targeted improvements across key areas such as access control, training, configuration management, and incident detection. These updates are designed to reduce organizational risk, improve operational resilience, and ensure alignment with the **NIST Cybersecurity Framework (CSF)** and **NIST SP 800-53** controls.

---

## Policy Recommendations

| **Policy Section**                    | **Recommended Change(s)**                                                                                     | **Reasoning**                                                                                                                                 |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| **1. Access Control**                | - Automatically lock workstations after inactivity<br>- Prohibit non-privileged accounts from executing privileged functions | NIST AC-11 requires session lock controls. Allowing non-privileged users to perform privileged functions violates NIST AC-6. Enforces least privilege and reduces insider threat risk. |
| **2. Awareness and Training**        | - Tailor training to employee roles<br>- Conduct periodic refresher training                                   | NIST AT-3 and AT-2 mandate role-based, ongoing training. This ensures relevance, enhances threat awareness, and promotes compliant behavior. |
| **3. Configuration Management**      | - Restrict software installations to authorized personnel<br>- Require documentation and approval for system changes | NIST CM-5 and CM-3 require strict controls to prevent configuration drift and unauthorized changes, reducing vulnerability exposure.         |
| **6. Physical & Environmental Protection** | - Review and revoke server room access as needed                                                              | NIST PE-2 and PE-3 call for periodic reviews of physical access. Revoking outdated access is essential for maintaining facility security.     |
| **7. Risk Assessment**               | - Formalize periodic risk assessments<br>- Document findings and mitigation actions                            | NIST RA-3 and RA-5 stress consistent, documented risk assessments. Supports audit readiness and proactive threat response.                    |
| **8. System & Information Integrity**| - Establish automated alerts and centralized logging for integrity issues                                      | NIST SI-4 recommends automated monitoring. Manual alerts delay response time. Automation improves incident detection and response speed.     |

---

## Conclusion

Implementing these policy updates strengthens the organization’s ability to identify, assess, and respond to both technical and operational risks. These recommendations:

- Align the organization with NIST 800-53 and other security frameworks
- Promote least privilege, secure configurations, and role-based accountability
- Improve readiness for audits, compliance checks, and real-world threats

Ongoing review and enforcement of these controls will ensure sustained risk mitigation and continued regulatory compliance in a dynamic threat landscape.

---

## Project Credit  
- **Project Executed & Presented By**: **Mohammad Aminul Islam** (Cloud Security Analyst)  
- **Project Source**: Google Cloud Security Command Center hands-on project (Coursera)  
- **Guidance & Framework**: Google Cloud documentation & instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  

