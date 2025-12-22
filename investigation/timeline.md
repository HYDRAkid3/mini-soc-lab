# Incident Timeline – SSH Brute Force Attack

## Overview
This timeline reconstructs the SSH brute force incident observed on the Ubuntu endpoint monitored by Wazuh.

---

## Timeline of Events

- **T0** – Attacker initiated SSH brute force attempts from Kali Linux
- **T1** – Multiple SSH authentication failures detected by Wazuh
- **T2** – Successful SSH authentication observed
- **T3** – Privileged command execution detected (`sudo`)
- **T4** – Fail2Ban threshold exceeded
- **T5** – Attacker IP blocked (SSH access refused)
- **T6** – No further SSH authentication alerts observed

---

## Outcome
The incident was successfully detected, investigated, and contained using automated response controls.
