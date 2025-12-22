# Analyst Decision Log

## Why This Was Treated as an Incident
- Repeated authentication failures
- Successful login following failures
- Privileged activity observed
- MITRE ATT&CK mapping to T1110 (Brute Force)

## Why Automated Response Was Appropriate
- Clear brute force behavior
- Known attack surface (SSH)
- Low risk of false positive
- Immediate containment reduced further risk

## Why No Further Escalation Was Required
- Single endpoint affected
- No lateral movement observed
- Attacker blocked successfully
