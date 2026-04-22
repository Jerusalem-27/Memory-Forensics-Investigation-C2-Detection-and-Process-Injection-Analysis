# Memory Forensics Investigation: Detecting C2, Process Injection, and Privilege Escalation

---

##  Overview  

This project focuses on analyzing a system memory image to detect signs of compromise and understand attacker behavior. By examining volatile memory artifacts, the investigation identified malicious activity including command execution, external communication, privilege escalation, and process injection.

The goal of this project is to demonstrate how real-world attacks can be uncovered through memory analysis and how attackers operate in stealth using in-memory techniques.

---

## Detection Summary  
 
The detection approach focuses on identifying malicious activity from volatile memory by analyzing process behavior, execution patterns, and network artifacts.

Instead of relying on disk-based indicators, this investigation uses in-memory evidence to uncover evasive attacker techniques.

Detection logic includes:

Identifying suspicious processes from non-standard or user-controlled locations
Detecting hidden or unlinked processes through cross-view analysis
Correlating processes with network connections to identify C2 activity
Detecting privilege escalation through process context and tokens
Identifying process injection into legitimate system processes
Extracting and analyzing in-memory payloads

This approach demonstrates how attackers operate in memory and how analysts can detect threats that leave little or no trace on disk.

---

## Attack Scenario  

The attacker gained access to the system and executed malicious commands directly in memory.

To avoid detection, the attacker:
- Established a reverse shell connection (C2 communication)  
- Escalated privileges to gain higher system access  
- Injected malicious code into legitimate processes  
- Used in-memory execution to reduce disk artifacts  

This allowed the attacker to operate stealthily while maintaining control over the system.

---

## Key Findings  

- High: Active connection to external C2 server (port 4444)  
- High: Privilege escalation observed  
- High: Process injection into legitimate system process  
- High: Suspicious processes executed from user directories  
- Medium: Malicious payloads identified in memory  

---
## Detection Focus  

- Suspicious process execution  
- Hidden and injected processes  
- Abnormal parent-child relationships  
- Unauthorized outbound network connections  
- Privilege escalation behavior  

---

## Data Source  

- Memory Image (RAM Dump)

---

## Tools & Technologies  

- Volatility Framework  
- Paraben E3  
- FTK Imager  
- DensityScout  

---

##  Security Improvements (Recommended)  
- Monitor and restrict outbound connections to unknown IP addresses  
- Implement Endpoint Detection and Response (EDR) solutions  
- Enforce least privilege access controls  
- Detect abnormal process execution and relationships  
- Monitor for process injection techniques  
- Perform continuous memory-based threat hunting  

---

## Skills Demonstrated  
- Memory Forensics (Volatility)  
- Threat Hunting & Attack Analysis  
- Process & Privilege Analysis  
- Detection of C2 Communication  
- Process Injection Detection  
- Evidence Correlation & Attack Reconstruction  

---

## Skills Demonstrated  

- Memory Forensics  
- Threat Hunting  
- Process Analysis  
- Network Artifact Analysis  
- Privilege Escalation Detection  
- Process Injection Detection  
- Attack Reconstruction  

---

## Why This Project Matters  

Many advanced attacks operate entirely in memory to avoid detection by traditional security tools. This project demonstrates how memory analysis can uncover hidden threats and provide visibility into attacker behavior that would otherwise remain undetected.

---

## Conclusion  

This investigation successfully identified multiple indicators of compromise and reconstructed attacker activity using memory artifacts. It highlights the importance of memory forensics in modern incident response and threat detection.

---

##  Disclaimer  
This investigation was performed for defensive security and threat detection purposes in a controlled environment using simulated data.
