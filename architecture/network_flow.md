# Network Flow – Mini SOC Lab

| Source        | Destination        | Port  | Purpose |
|---------------|--------------------|-------|---------|
| Kali Linux    | Ubuntu Endpoint     | 22    | SSH attacks |
| Ubuntu Agent  | Wazuh Manager       | 1514  | Agent communication |
| Ubuntu Agent  | Wazuh Authd         | 1515  | Agent enrollment |
| Analyst PC    | Wazuh Dashboard     | 5601  | Web UI access |


## Traffic Flow
1. Kali Linux initiates SSH traffic to Ubuntu endpoint.
2. Ubuntu SSH logs authentication attempts.
3. Wazuh Agent forwards logs to Wazuh Manager.
4. Wazuh Manager analyzes events.
5. Alerts stored in Wazuh Indexer.
6. Analyst views alerts via Wazuh Dashboard.

## Key Ports
- SSH: 22
- Wazuh Agent → Manager: 1514/1515
- Dashboard: 443
