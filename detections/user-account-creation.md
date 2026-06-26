# User Account Creation Detection

## Objective

Detect creation of new user accounts on a monitored Windows endpoint.

## Attack Simulation

The following command was executed:

```cmd
net user TestUser Password@123 /add
```

## Detection

Wazuh successfully collected the Windows Security Event and generated an alert indicating a new local user account was created.

## Investigation

* Host: Windows 11 Endpoint
* Event Source: Windows Security Logs
* Action: User Account Created
* User: TestUser

## Impact

Unauthorized user creation may indicate privilege abuse or persistence mechanisms used by attackers.

## MITRE ATT&CK

T1136 - Create Account
