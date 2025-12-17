\# Mini SOC Lab (Wazuh + Docker)



This repository contains a hands-on Security Operations Center (SOC) lab built

using Wazuh and Docker. The project demonstrates centralized log collection,

alert detection, and investigation workflows through realistic attack

simulations.



\## Architecture



!\[SOC Architecture Diagram](architecture/architecture\_diagram.png)



This architecture represents a simplified SOC environment where security events

from an Ubuntu endpoint are collected by a Wazuh agent, processed by the Wazuh

manager and indexer, and visualized through the Wazuh dashboard for analyst

review.



\## Tech Stack

\- Wazuh (SIEM + EDR)

\- Docker \& Docker Compose

\- Ubuntu Linux (Monitored Endpoint)

\- Kali Linux (Attack Simulation)

\- Git \& GitHub



\## Project Scope

\- Centralized log ingestion

\- SSH brute-force detection

\- Basic attack investigation and reporting

\- SOC-style documentation and playbooks



\## Status

🚧 In progress — attack scenarios, detections, and investigation reports are

being added.



