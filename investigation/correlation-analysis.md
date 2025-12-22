# Correlation Analysis – SSH Brute Force Incident

## Why Correlation Matters
A single `sshd: authentication failed` alert is common and often benign. However, SOC analysts must identify patterns that indicate malicious intent.

This incident demonstrates how low-severity alerts combine into a high-confidence security event.

---

## Observed Alert Chain

1. Multiple SSH authentication failures  
   - Rule: `sshd: authentication failed`
   - Severity: Medium (Level 5)

2. Successful SSH login
   - Indicates credential compromise or password guessing success.

3. Privileged activity detected
   - `Successful sudo to ROOT executed`
   - Confirms attacker escalation.

---

## Correlated Incident Narrative

- Initial brute force activity detected from `10.0.0.226`
- Repeated failed login attempts over a short time window
- Eventual successful authentication
- Immediate privileged command execution

This sequence confirms **account compromise**, not a false positive.

---

## SOC Incident Grouping Logic

| Signal | Alone | Correlated |
|------|------|-----------|
| SSH failed login | Low | Medium |
| SSH success | Medium | High |
| Sudo activity | Medium | Critical |

When combined, these alerts form a **single security incident**.

---

## Analyst Decision
✅ Confirmed Incident  
❌ Not a false positive  
🔺 Escalation required

---

## Improvement Opportunity
Implement correlation rules that trigger high-severity alerts only when:
- Multiple failures occur AND
- A success follows within a defined time window
