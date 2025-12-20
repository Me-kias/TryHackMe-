# TryHackMe – Offensive Security

**Concept:**  
To outsmart a hacker, you must think like one. Offensive Security focuses on simulating real hacker behavior to identify vulnerabilities and strengthen defenses.

**Activity:**  
This lesson demonstrates how ethical hackers operate by legally hacking a website in a safe environment.

**Key Point:**  
Simulating a hacker’s actions to find system vulnerabilities is known as **Offensive Security**.

# TryHackMe – Your First Hack (Gobuster)

**Setup:**  
TryHackMe uses virtual machines to simulate real-world environments. In this lesson, a fake banking app called **FakeBank** is used for safe, legal practice.

**Tool Used:**  
**Gobuster** – a command-line tool used to brute-force hidden directories and pages on a website using a wordlist.

**Process:**  
Gobuster was run against `http://fakebank.thm`, which revealed a hidden page:  
`/bank-transfer`

**Exploit:**  
The exposed bank transfer page allowed unauthorized money transfers due to missing access controls.

**Result:**  
$2000 was successfully transferred from account **2276** to account **8881**, confirming the vulnerability.

**Key Point:**  
Hidden and unprotected admin pages can lead to serious security breaches if not properly secured.
