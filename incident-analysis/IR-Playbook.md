# Incident Response Playbook

## Purpose
Document detection, triage, containment
and lessons learned for each simulated
attack technique.

## Incidents

### INC-001: Credential Dumping (T1003.001)
**Severity:** CRITICAL
**Time:** July 23 @ 14:14:57

**Detection:**
Wazuh Rule Level 15
"Executable file dropped in folder
commonly used by malware"

**Triage:**
Verdict: TRUE POSITIVE
Evidence: LSASS targeted, files dropped
in temp folder, Mimikatz patterns detected

**Containment:**
→ Isolate endpoint
→ Kill process tree
→ Reset all passwords
→ Preserve memory forensics

**Lessons Learned:**
→ Default rules caught file drop
→ LSASS access itself not detected
→ Custom Rule 100001 written to fix gap

---

### INC-002: Encoded PowerShell (T1059.001)
**Severity:** HIGH
**Time:** July 25 @ 11:50:30

**Detection:**
Custom Rule 100003 fired 3 times
"Encoded PowerShell execution detected"

**Triage:**
Verdict: TRUE POSITIVE
Evidence: -enc flag detected in commandline
Multiple instances in 3 seconds

**Containment:**
→ Block PowerShell via AppLocker
→ Enable Constrained Language Mode
→ Decode and analyze payload

**Lessons Learned:**
→ Default severity too low (Level 4)
→ Custom rule raised to Level 12
→ Encoding always suspicious in enterprise

---

### INC-003: Scheduled Task (T1053.005)
**Severity:** MEDIUM

**Detection:** Windows Event ID 4698
**Verdict:** TRUE POSITIVE
**Lessons:** Persistence needs higher priority

---

### INC-004: Account Discovery (T1087.001)
**Severity:** LOW-MEDIUM

**Detection:** Sysmon process creation
**Verdict:** TRUE POSITIVE
**Lessons:** Hard to distinguish from admin
activity — need behavioral baseline

---

### INC-005: System Discovery (T1082)
**Severity:** LOW

**Detection:** Sysmon process events
**Verdict:** TRUE POSITIVE
**Lessons:** Low risk alone — dangerous
when correlated with other techniques
