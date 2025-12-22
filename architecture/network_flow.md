# Network Flow

| Source        | Destination        | Port  | Purpose |
|---------------|--------------------|-------|---------|
| Kali Linux    | Ubuntu Endpoint     | 22    | SSH attacks |
| Ubuntu Agent  | Wazuh Manager       | 1514  | Agent communication |
| Ubuntu Agent  | Wazuh Authd         | 1515  | Agent enrollment |
| Analyst PC    | Wazuh Dashboard     | 5601  | Web UI access |
