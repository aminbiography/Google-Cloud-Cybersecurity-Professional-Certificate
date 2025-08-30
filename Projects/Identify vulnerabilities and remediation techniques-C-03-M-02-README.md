# Identify Vulnerabilities and Apply Remediation Techniques

---

## Project Title

**Secure Web Application Testing and Vulnerability Remediation**

---

## Objectives

- To identify security vulnerabilities in a web application before deployment.
- To simulate a real-world attack scenario using **Cross-Site Scripting (XSS)**.
- To scan the application with Google Cloud’s **Web Security Scanner**.
- To remediate vulnerabilities through secure coding practices.
- To verify the effectiveness of remediation by re-scanning.

---

## Project Description

This project was conducted in a cloud environment to evaluate the security posture of a newly developed **Cymbal Bank corporate banking portal**.

The project steps included:

1. **Setup Environment**

   - Launched a **Google Cloud VM** with a static IP address.
   - Deployed a Python Flask-based application designed to demonstrate XSS vulnerabilities.

![Identify vulnerabilities and remediation techniques](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Identify%20vulnerabilities%20and%20remediation%20techniques-01.png?raw=true)


2. **Simulate Exploitation**

   - Injected a **malicious XSS payload** (`<script>alert('XSS')</script>`) to confirm the vulnerability.
   - Verified that the application executed the injected script, proving exploitable weakness.

![Identify vulnerabilities and remediation techniques](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Identify%20vulnerabilities%20and%20remediation%20techniques-02.png)

3. **Vulnerability Scanning**

   - Configured and executed **Google Cloud Web Security Scanner**.
   - Scanner identified **Cross-Site Scripting vulnerabilities**, confirming the risk.

![Identify vulnerabilities and remediation techniques](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Identify%20vulnerabilities%20and%20remediation%20techniques-03.png)

4. **Remediation**

   - Modified the **application code (app.py)** to **escape user-supplied input** instead of rendering it as raw HTML.
   - Applied secure coding techniques to prevent malicious code execution.

   Example of remediation:

   ```python
   output_string = "".join([html_escape_table.get(c, c) for c in input_string])
   # output_string = input_string
   ```

![Identify vulnerabilities and remediation techniques](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Identify%20vulnerabilities%20and%20remediation%20techniques-04.png)

5. **Validation**
   - Re-ran the Web Security Scanner after remediation.
   - Verified that **no vulnerabilities were found**, confirming successful remediation.

![Identify vulnerabilities and remediation techniques](https://github.com/aminbiography/Google-Cloud-Cybersecurity-Professional-Certificate/blob/main/bar-graph-chart-image/Identify%20vulnerabilities%20and%20remediation%20techniques-05.png)

---

## Conclusion

- This project highlighted the importance of **proactive vulnerability management**.
- By simulating attacks, scanning, and applying fixes, we demonstrated how organizations can **mitigate risks before production deployment**.
- Key takeaways:
  - Early detection and remediation reduce costs and risks.
  - Secure coding practices (e.g., escaping untrusted input) are essential.
  - Regular scanning is critical to maintaining a **strong security posture**.

---

**Outcome:** The vulnerable application was successfully secured against **Cross-Site Scripting (XSS)**. This project showcased end-to-end **offensive testing and defensive remediation**, a core skill for cybersecurity and cloud security analysts.

---

## Project Credit
- **Lab Activity & Prepared By**: **Mohammad Aminul Islam** (Cloud Security Analyst).  
- **Lab Source**: Google Cloud Security Command Center hands-on lab (Qwiklabs / Coursera)  
- **Guidance & Framework**: Google Cloud documentation & Qwiklabs instructions  
- **Copyright**: © 2022 Google LLC. Google and the Google logo are trademarks of Google LLC. Other names may be trademarks of their respective companies.  
