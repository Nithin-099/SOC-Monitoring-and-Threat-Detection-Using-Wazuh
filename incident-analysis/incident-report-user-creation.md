Incident Name:
User Account Creation Detection

Severity:
Medium

Description:
A new local Windows user account was created.

Detection Source:
Windows Security Logs

Detection Tool:
Wazuh SIEM

Command Executed:
net user TestUser Password@123 /add

Investigation:
The event was detected by Wazuh and correlated with Windows security logs.

MITRE ATT&CK:
T1136 - Create Account

Recommendation:
Monitor unauthorized account creation and enforce least privilege access.
