# TryHackMe – Defensive Security

**Concept:**  
Defensive Security focuses on preventing intrusions, detecting attacks, and responding effectively when incidents occur. It works alongside offensive security to strengthen overall system protection.

**Key Responsibilities:**  
- User cybersecurity awareness  
- Asset documentation and management  
- System updates and patching  
- Firewalls and intrusion prevention systems (IPS)  
- Logging and monitoring for threat detection  

**Related Areas:**  
SOC, Threat Intelligence, DFIR, and Malware Analysis.

**Key Point:**  
The team responsible for defensive security is known as the **Blue Team**.

# TryHackMe – SOC & DFIR

**Security Operations Center (SOC):**  
A SOC is a team of cybersecurity professionals responsible for monitoring networks and systems to detect vulnerabilities, policy violations, unauthorized activity, and network intrusions. One of its key functions is using **Threat Intelligence** to understand adversaries and anticipate attacks.

**Threat Intelligence:**  
Threat intelligence involves collecting, processing, and analyzing data from logs, public sources, and other inputs to identify threat actors, understand their tactics, and build a threat-informed defense strategy.

**Digital Forensics and Incident Response (DFIR):**  
DFIR stands for **Digital Forensics and Incident Response** and focuses on investigating cyber incidents, analyzing evidence, responding to attacks, and restoring systems while minimizing damage.

**Incident Response Phases:**  
Preparation, Detection & Analysis, Containment/Eradication/Recovery, and Post-Incident Activity.

**Malware Analysis:**  
Malware analysis studies malicious software using static and dynamic techniques to understand behavior and impact. A type of malware that encrypts files and demands payment for recovery is known as **ransomware**.

# TryHackMe – SIEM Scenario

**Scenario:**  
Acted as a SOC analyst protecting a bank using a **SIEM** tool to monitor security events and investigate alerts.

**Key Learning:**  
Not all alerts are malicious. Analysts must evaluate events such as failed login attempts and connections from unknown IP addresses to determine whether they represent real threats.

**Hands-On Exercise:**  
Interacted with a simulated SIEM environment to analyze alerts and identify suspicious activity.

**Result:**  
The investigation led to the discovery of the flag **THM{THREAT-BLOCKED}**, confirming successful threat detection and response.

**Next Step:**  
Continue learning with the *Search Skills* lesson to improve investigation and research techniques.
