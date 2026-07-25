# Lab Setup Guide

## Prerequisites
- VirtualBox installed
- 16GB RAM minimum
- 60GB free storage

## Architecture

Windows 11 Host (Victim)

+ VirtualBox
  └── Ubuntu Server 22.04 (Wazuh SIEM)
      IP: 192.168.56.101

## Step 1 — VirtualBox Network
Create Host-Only network:

- IP: 192.168.56.1

- Subnet: 255.255.255.0

- DHCP: Enabled

## Step 2 — Ubuntu Server VM

- RAM: 4GB

- Storage: 25GB

- Adapter 1: NAT

- Adapter 2: Host-Only

## Step 3 — Install Wazuh

curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh

sudo bash wazuh-install.sh -a

Access dashboard:

https://192.168.56.101

User: admin

## Step 4 — Install Sysmon on Windows

Download Sysmon from Sysinternals

Use SwiftOnSecurity config:

.\Sysmon64.exe -accepteula -i sysmonconfig.xml

## Step 5 — Install Wazuh Agent on Windows

Download wazuh-agent-4.7.0-1.msi

Run:

msiexec.exe /i wazuh-agent.msi /q

WAZUH_MANAGER="192.168.56.101"

WAZUH_AGENT_NAME="Windows-Victim"

NET START WazuhSvc

## Step 6 — Install Atomic Red Team

Set-ExecutionPolicy Bypass -Scope CurrentUser

IEX (IWR 'https://raw.githubusercontent.com/

redcanaryco/invoke-atomicredteam/master/

install-atomicredteam.ps1' -UseBasicParsing)

Install-AtomicRedTeam -getAtomics -Force

## Verification

Wazuh Dashboard → Agents

Should show Windows agent as Active ✅
