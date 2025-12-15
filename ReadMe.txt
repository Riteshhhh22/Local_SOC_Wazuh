Local SOC Environment using Wazuh

OVERVIEW
This project demonstrates the design and implementation of a local Security Operations Center (SOC) lab using Wazuh SIEM.
The environment simulates real-world detection scenarios by generating controlled attack activity and validating how a SIEM
collects logs, correlates events, and raises security alerts across multiple operating systems.

The focus of this lab is on detection, monitoring, and alert analysis from a SOC analyst’s perspective.

--------------------------------------------------

LAB ARCHITECTURE
The SOC environment is deployed within an isolated virtual network to ensure safe and controlled testing.

Components:
- Wazuh Manager (Ubuntu) – Central SIEM and alerting platform
- Windows 10, Ubuntu, CentOS – Monitored endpoints with Wazuh agents
- Kali Linux – Attacker machine for controlled security testing
- Network: Isolated subnet (192.168.80.0/24)

--------------------------------------------------

DETECTION SCENARIOS IMPLEMENTED
The following security events were intentionally generated and successfully detected by Wazuh:

1. File Integrity Monitoring (FIM)
   - Detection of file creation, modification, and deletion on Linux and Windows endpoints.

2. Brute-Force Authentication Attempts
   - Simulated SSH and RDP brute-force activity detected via Linux and Windows security logs.

3. SQL Injection Attempts
   - Suspicious SQL patterns detected from Apache web server access logs.

Each scenario was verified using Wazuh alerts, rule IDs, timestamps, severity levels, and source IP correlation.

--------------------------------------------------

TOOLS & TECHNOLOGIES
- SIEM: Wazuh Manager and Wazuh Agents
- Operating Systems: Ubuntu, CentOS, Windows 10, Kali Linux
- Security Tools: Nmap, Hydra, curl
- Logging Sources: Apache access logs, Linux authentication logs, Windows security logs
- Risk Assessment: CVSS v3.1
- Virtualization: VMware / VirtualBox

--------------------------------------------------

METHODOLOGY
The lab follows a structured workflow inspired by the Penetration Testing Execution Standard (PTES):
1. Reconnaissance and service discovery
2. Controlled attack execution
3. Log generation on target systems
4. Alert verification and analysis in Wazuh
5. Risk assessment and remediation planning

This approach helps directly link attacker actions with SOC detections.

--------------------------------------------------

FINDINGS SUMMARY
- File Integrity Monitoring: Medium severity – file tampering detected immediately
- Brute-Force Authentication: High severity – repeated login failures flagged in real time
- SQL Injection: High severity – malicious patterns detected from web logs

--------------------------------------------------

REMEDIATION & IMPROVEMENTS
- Enforce strict file permissions and real-time FIM monitoring
- Implement account lockouts, MFA, and rate-limiting
- Restrict SSH/RDP exposure and harden authentication policies
- Use parameterized queries and input validation for web applications
- Tune SIEM rules to reduce noise and highlight critical alerts

--------------------------------------------------

WHAT THIS PROJECT DEMONSTRATES
- Practical SOC-level understanding of SIEM deployment
- Log analysis and alert interpretation across multiple platforms
- Detection-focused (blue-team) security mindset
- Ability to explain attacker behaviour from a defender’s perspective

--------------------------------------------------

DOCUMENTATION
A detailed technical report including architecture diagrams, PoCs, screenshots, CVSS ratings,
and remediation steps is included in the Report folder of this repository.

--------------------------------------------------

DISCLAIMER
This project was conducted strictly for educational purposes in a controlled lab environment.
All attacks were simulated against systems owned and configured by the author.

--------------------------------------------------

AUTHOR
Ritesh Indore
MSc Cybersecurity – National College of Ireland
CompTIA Security+ Certified
