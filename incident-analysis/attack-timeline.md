# Attack Simulation Timeline

## Exercise Details
Date: July 23-25, 2026
Analyst: Nithin
Environment: Home SOC Lab
Framework: MITRE ATT&CK Enterprise

## Timeline

### July 23, 2026
| Time | Event | MITRE ID | Result |
|------|-------|----------|--------|
| 14:02 | Lab initialized | — | ✅ Ready |
| 14:07 | System Discovery | T1082 | ✅ Detected |
| 14:10 | Account Discovery | T1087.001 | ✅ Detected |
| 14:14 | PowerShell Execution | T1059.001 | ✅ Detected |
| 14:14 | Credential Dumping | T1003.001 | ✅ Detected |
| 14:15 | Scheduled Task | T1053.005 | ✅ Detected |
| 14:15 | AV Block | T1003.001-13 | ✅ Blocked |

### July 25, 2026
| Time | Event | Result |
|------|-------|--------|
| 11:50 | Custom rules deployed | ✅ |
| 11:50 | Rule 100003 fired | ✅ 3 times |
| 11:50 | T1059.001 detected | ✅ |

## Detection Summary

Total Attacks: 5
Total Detected: 5
Detection Rate: 100%
Custom Rules: 5 written
Rules Fired: 1 confirmed
AV Blocks: 1

## Attack Chain Analysis

RECON → EXECUTION → CRED ACCESS → PERSISTENCE
T1082 T1059 T1003 T1053
T1087 ↓ ↓ ↓
↓ Detected Detected Detected
Detected Level 4 Level 15 Level 10
