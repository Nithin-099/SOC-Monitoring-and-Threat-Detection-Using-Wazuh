# Custom Detection Rules Summary

## Overview
5 custom Wazuh rules written to close

gaps identified in default ruleset during

attack simulation exercise.

## Rules Table

| Rule ID | Severity | MITRE ID | Technique | Trigger |
|---------|----------|----------|-----------|---------|
| 100001 | CRITICAL (15) | T1003.001 | LSASS Access | lsass.exe targeted |
| 100002 | HIGH (12) | T1003.001 | Mimikatz | mimikatz/sekurlsa keyword |
| 100003 | HIGH (12) | T1059.001 | Encoded PS | -enc/-encodedcommand |
| 100004 | MEDIUM (10) | T1053.005 | Sched Task | schtasks /create |
| 100005 | MEDIUM (8) | T1087.001 | Acct Enum | net user/whoami |

## Rules That Fired During Testing
| Rule ID | Times Fired | Date |
|---------|-------------|------|
| 100003 | 3 times | July 25, 2026 |

## Detection Gaps Found

Default Wazuh rules missed:


- LSASS direct memory access

- Encoded PowerShell specifically

- Mimikatz keywords in commandline

## How to Deploy

Copy local_rules.xml content to:

/var/ossec/etc/rules/local_rules.xml

Then restart:

sudo systemctl restart wazuh-manager
