🔐 SSH Brute Force Attack – Simulation

This document describes a simulated SSH brute force attack executed within the SOC lab environment.  
The scenario is designed to generate authentication-related telemetry and validate detection, investigation, and alerting capabilities in **Wazuh**.

> ⚠️ **Disclaimer**  
> This activity was conducted in an isolated lab environment for **educational and defensive security purposes only**.

---

## 1. Objective

- Simulate credential brute force activity against an SSH service
- Generate multiple failed SSH authentication attempts
- Achieve a successful SSH login
- Validate Wazuh detection rules and MITRE ATT&CK mapping
- Produce telemetry suitable for SOC investigation workflows

---

## 2. Environment Overview

| Role              | Operating System   | IP Address     | Notes                              |
|-------------------|--------------------|----------------|------------------------------------|
| Attacker          | Kali Linux         | `10.0.0.226`   | Untrusted external attacker machine |
| Target / Victim   | Ubuntu             | `10.0.0.95`    | Monitored endpoint with Wazuh Agent |

**Target Service**  
- Service: OpenSSH  
- Port: 22

---

## 3. Tools Used

- Kali Linux
- THC-Hydra
- Nmap
- OpenSSH
- Wazuh (Agent + Manager + Indexer + Dashboard)

---

## 4. Attack Phases

### 4.1 Reconnaissance

Command used to verify SSH service availability:

```bash


nmap -p 22 10.0.0.95
Result
textPORT     STATE SERVICE
22/tcp   open  ssh
→ Confirmed SSH service is exposed and accessible.
4.2 Brute Force Execution
Command executed using THC-Hydra:
Bashhydra -l ubuntu -P passwords.txt ssh://10.0.0.95
Observed behavior

Multiple failed authentication attempts
One eventual successful login

This pattern is very representative of real-world SSH brute-force attacks.

5. Detection & Logging Flow

SSH daemon on Ubuntu logs failed & successful authentications
Wazuh Agent collects the logs
Events forwarded to Wazuh Manager
Rule matching → Alert generation
Alerts visible in Wazuh Dashboard (Threat Hunting → Events)

Detected activity included:

High volume of SSH authentication failures
Successful login after repeated failures


6. MITRE ATT&CK Mapping















IDTechniqueTacticT1110Brute ForceCredential Access

7. Evidence (Screenshots)

SSH Service Discovery
screenshots/nmap_scan_ubuntu.png
Brute Force Attack Execution (Hydra)
screenshots/hydra_bruteforce.png
Wazuh Detected Events
screenshots/wazuh_ssh_failed_events.png


8. Outcome & Learnings
This simulation successfully demonstrated:

Generation of realistic SSH brute force telemetry
Reliable log collection and forwarding by Wazuh Agent
Accurate detection and alerting by Wazuh
Clear mapping to MITRE ATT&CK T1110
Good foundation for SOC alert triage, investigation & response validation


textYou can now copy the entire block above and paste it directly into your GitHub file `ssh-bruteforce.md`.  
Good luck with your lab documentation! 🛡️
