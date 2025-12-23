# ⚠️ Common Pitfalls & Lessons Learned

Almost everyone hits these issues — including experienced analysts.

---

## 🔴 No Alerts Appearing
Common causes:
- Agent not registered
- Wrong log paths
- Time desynchronization

Fix:
- Verify agent status
- Check timestamps
- Restart services carefully

---

## 🔴 SSH Attacks Not Logged
Common causes:
- SSH disabled
- Wrong authentication method
- Log level misconfiguration

Fix:
- Verify SSH configuration
- Confirm auth logging enabled

---

## 🔴 Fail2Ban Interfering With Testing
Fail2Ban may:
- Block Kali prematurely
- Hide full attack patterns

Fix:
- Disable Fail2Ban during attack simulation
- Enable it **after** investigation

---

## 🔴 Confusing Timelines
Cause:
- VM clocks out of sync

Fix:
- Sync time on all machines
- Always validate timestamps before conclusions

---

## 🧠 Key Lesson

SOC work is messy.
Logs are noisy.
Perfect setups don’t exist.

Learning to **debug the environment** is part of becoming an analyst.
