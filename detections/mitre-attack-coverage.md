# MITRE ATT&CK Coverage Map

## Techniques Tested

| Tactic | Technique | ID | Tool | Wazuh Default | Custom Rule |
|--------|-----------|-----|------|---------------|-------------|
| Execution | PowerShell | T1059.001 | ART | Level 4 | Rule 100003 ✅ |
| Credential Access | LSASS Memory | T1003.001 | ART | Level 15 | Rule 100001 |
| Persistence | Scheduled Task | T1053.005 | ART | Level 4 | Rule 100004 |
| Discovery | Account Discovery | T1087.001 | ART | Level 4 | Rule 100005 |
| Discovery | System Info | T1082 | ART | Level 3 | — |

## Attack Chain Observed

T1082 (Recon)
↓
T1087 (Account Discovery)
↓
T1059 (Execution)
↓
T1003 (Credential Dumping)
↓
T1053 (Persistence)


## Coverage Screenshot
![ATT&CK Heatmap](../screenshots/mitre-heatmap.png)

## Key Insight
These 5 techniques together representa complete attack chain matching real APT behavior documented in MITRE ATT&CK.

Individual alerts are low priority.

Combined in sequence = critical incident.
