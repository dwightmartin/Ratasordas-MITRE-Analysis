# **Ratasordas Technologies: MITRE ATT\&CK Analysis**

### **Project Overview**

This document presents a tactical analysis of the fictional company Ratasordas Technologies security incident, using the **MITRE ATT\&CK framework**. This approach focuses on the adversary's techniques and tactics to provide a deeper understanding of the attack chain. The analysis translates the incident into a structured framework, which is then used to inform strategic recommendations for improving the company's security posture.

### **Incident Analysis: The MITRE ATT\&CK Matrix**

The following table maps the actions of the malicious threat actor to specific tactics and techniques from the MITRE ATT\&CK framework.

| Tactic | Technique ID | Technique Name | Description |
| :---- | :---- | :---- | :---- |
| **Reconnaissance** | T1589 | Gather Victim Identity Information | The threat actor was known to the CEO, indicating they likely conducted reconnaissance to identify key personnel and targets within the company. |
|  | T1587 | Develop Capabilities | The actor's ability to locate a specific employee and gain physical access suggests they developed a social engineering or physical access plan prior to the attack. |
| **Initial Access** | T1199 | Trusted Relationship | The threat actor used a "trusted relationship" with an employee to gain unauthorized access to the premises, which set the stage for the cyberattack. |
|  | T1133 | External Remote Services | The unconfigured developer server exposed an external remote service, which was the vulnerability that provided the initial digital access for the attack. |
| **Credential Access** | T1078 | Valid Accounts | The lack of **Multi-Factor Authentication (MFA)** on the developer's server likely allowed the threat actor to use a compromised password to access a valid account and execute their plan. |
| **Impact** | T1499 | Endpoint Denial of Service | The deletion of graphics from the server caused a denial of service to the application, rendering it useless for all users. |
|  | T1486 | Data Manipulation | The malicious actor directly manipulated data by deleting the graphics. The impact of this data manipulation was a denial of service. |

### **Detection and Remediation Actions**

Based on the MITRE ATT\&CK matrix, the following table outlines specific detection and remediation actions to mitigate similar threats in the future.

| Tactic | Technique ID | Detection & Remediation Action |
| :---- | :---- | :---- |
| **Initial Access** | T1133 (External Remote Services) | Implement a formal policy to disable all non-essential remote services on third-party servers. All necessary services should be protected by a VPN. |
| **Credential Access** | T1078 (Valid Accounts) | Enforce Multi-Factor Authentication (MFA) on all critical accounts and implement password complexity requirements to prevent unauthorized access. |
| **Impact** | T1486 (Data Manipulation) | Implement file integrity monitoring on all critical data assets to alert on unauthorized deletions or modifications in real-time. |

### **Strategic Recommendations**

Based on the MITRE ATT\&CK analysis, the company's security strategy should focus on hardening its defenses against the specific tactics and techniques used in this attack.

1. **Reduce Reconnaissance and Initial Access Vectors:**  
   * **Physical Security:** Implement a strict visitor policy that requires all guests to be pre-registered and escorted at all times.  
   * **Vendor Management:** Implement a formal **vendor risk management (VRM) program** that proactively vets third-party relationships and enforces minimum security standards.  
2. **Strengthen Credential Access Controls:**  
   * **Enforce MFA:** Mandate **Multi-Factor Authentication (MFA)** for all critical servers and third-party accounts to prevent a single compromised password from granting unauthorized access.  
   * **Endpoint Security:** Implement a policy of **zero trust** for all internal and third-party systems, ensuring access is granted on a least-privilege basis.  
3. **Enhance Detection and Recovery Capabilities:**  
   * **Automated Monitoring:** Implement a centralized monitoring system to detect and alert on unusual activity, such as a high volume of file deletions, which could indicate a data manipulation attack in progress.  
   * **Backup & Recovery:** Reinforce the importance of a formalized backup and recovery plan with a standardized naming convention to reduce the **Recovery Time Objective (RTO)** and mitigate the impact of data manipulation attacks.

### **Proactive Threat Hunting**

The MITRE ATT\&CK framework provides a foundation for proactive threat hunting. This analysis will be used to develop a hunting plan that looks for similar activity in network logs and security information and event management (SIEM) systems. We will use the identified techniques (e.g., T1133, T1078) as indicators of compromise (IOCs) to search for potential adversary activity that may not have triggered an automated alert.

### **Post-Incident Lessons Learned and Process Improvements**

* **Strategic Governance Failure:** The incident highlighted a critical failure in governance. We learned that we cannot rely on a third-party vendor to determine the criticality of an asset. The wordless nature of our app makes graphics a high-priority asset, and as such, we must be proactive in setting and enforcing security expectations for all vendors.  
* **Operational Process Failure:** The three-day recovery time was not due to a technical failure but a process failure. The lack of a standardized naming convention for graphics meant the team had to manually match and re-upload each file, which was a time-consuming and inefficient process.  
* **Business Impact and Remediation:** This delay was unacceptable from a business perspective, as it rendered our core product unusable and likely led to a loss of user trust and potential revenue. A new policy has since been implemented to use a standardized naming nomenclature for all graphics. This change allows for a **near-immediate recovery** in the future, dramatically reducing the potential for business disruption.

### **Skills Demonstrated**

This project showcases a range of advanced cybersecurity skills:

* **Threat Analysis:** Using a structured framework to analyze an attack from the adversary's perspective.  
* **Tactical and Strategic Thinking:** Mapping specific attack techniques to actionable, high-level security recommendations.  
* **Technical Communication:** Clearly articulating a complex security incident using industry-standard terminology.  
* **Proactive Mitigation:** Developing a plan to harden defenses against specific attack vectors, rather than just reacting to them.
