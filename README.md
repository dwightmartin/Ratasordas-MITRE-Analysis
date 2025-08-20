# **Ratasordas Technologies: MITRE Analysis Executive Summary**

### **Project Overview**

This document presents a tactical, threat-informed analysis of a security incident at Ratasordas Technologies. Using the **MITRE ATT\&CK framework**, this project dissects an attack that rendered the company's app unusable by deleting graphics from a third-party server. The analysis maps the adversary's actions to specific techniques, providing a strategic foundation for proactive defense and continuous improvement.

### **Attack Analysis Summary**

The threat actor's attack chain was mapped to several MITRE tactics, highlighting both technical and human-related vulnerabilities.

* **Reconnaissance & Initial Access:** The adversary gained access by leveraging a **"Trusted Relationship"** with an employee and exploiting an **"External Remote Service"** on an unconfigured developer server.  
* **Credential Access & Impact:** The lack of **Multi-Factor Authentication (MFA)** allowed the actor to use a "Valid Account" to perform **"Data Manipulation,"** which resulted in an indirect **"Endpoint Denial of Service"** to the application's users.

### **Strategic Recommendations**

Based on this analysis, the strategic recommendations focus on hardening the company's defenses against the specific techniques used in this attack:

* **Proactive Defense:** Implement a formal **vendor risk management (VRM) program** and enforce a **zero-trust** policy with mandatory **MFA** for all critical accounts to strengthen credential and initial access controls.  
* **Enhanced Monitoring:** Deploy a centralized monitoring system with **file integrity monitoring** to detect and alert on unauthorized data manipulation in real-time.  
* **Continuous Improvement:** A new policy has been implemented to use a standardized naming convention for all graphics, reducing the **Recovery Time Objective (RTO)** from three days to near-immediate.

### **Skills Demonstrated**

This project showcases an advanced understanding of cybersecurity, including **threat analysis**, **proactive mitigation**, **tactical and strategic thinking**, and the ability to translate technical findings into actionable, business-focused recommendations.
