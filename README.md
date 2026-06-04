# SOC Home Lab – SIEM Monitoring & Threat Detection Platform

## Overview

This project is a Security Operations Center (SOC) Home Lab designed to simulate real-world security monitoring, threat detection, and incident investigation workflows using Splunk Enterprise.

The environment consists of:

* AWS EC2 Ubuntu Server
* Windows Virtual Machine
* Kali Linux Attack Machine
* Splunk Enterprise SIEM
* Splunk Universal Forwarder
* Sysmon Endpoint Telemetry

The lab demonstrates log collection, detection engineering, threat hunting, attack simulation, dashboard development, alerting, and MITRE ATT&CK mapping.

---

## Architecture

```text
Kali Linux (Attacker)
        │
        ▼
Windows VM (Sysmon)
        │
        ▼
Splunk Universal Forwarder
        │
        ▼
AWS EC2 Ubuntu
Splunk Enterprise SIEM
        │
        ▼
Dashboards • Alerts • Investigations

Ubuntu Server (SSH Logs)
        │
        ▼
Splunk Enterprise
```

---

## Environment

### Infrastructure

* AWS EC2 Ubuntu Server
* Windows Virtual Machine
* Kali Linux Virtual Machine

### Security Tools

* Splunk Enterprise
* Splunk Universal Forwarder
* Sysmon

### Log Sources

* Windows Security Logs
* Sysmon Process Creation Events
* Sysmon Network Connection Events
* Linux Authentication Logs

---

## Detection Rules

### SSH Brute Force Detection

Detects repeated failed SSH authentication attempts.

### PowerShell Execution Detection

Detects PowerShell process execution using Sysmon Event ID 1.

### CMD Execution Detection

Detects Windows Command Prompt execution activity.

### External Network Connection Detection

Monitors outbound network connections using Sysmon Event ID 3.

---

## Dashboards

### Windows Monitoring Dashboard

Includes:

* Top Executed Processes
* Process Creation Trend
* PowerShell Activity Trend
* Top Destination Ports

### Linux Monitoring Dashboard

Includes:

* Failed SSH Logins
* Top Attacker IP Addresses
* SSH Attack Timeline
* Authentication Activity

---

## Attack Simulations

### SSH Brute Force Attack

* Source: Kali Linux
* Target: Ubuntu Server

### PowerShell Activity Simulation

* Generated PowerShell execution events
* Detected through Sysmon process creation monitoring

### Network Activity Monitoring

* Outbound network connections observed using Sysmon Event ID 3

### Nmap Reconnaissance

* Source: Kali Linux
* Target: Windows VM
* Result: Firewall filtered scan traffic

---

## MITRE ATT&CK Mapping

| Detection                | Technique |
| ------------------------ | --------- |
| SSH Brute Force          | T1110     |
| Password Guessing        | T1110.001 |
| PowerShell Execution     | T1059.001 |
| Command Prompt Execution | T1059.003 |
| Network Connections      | T1071     |
| Network Discovery        | T1049     |
| Nmap Reconnaissance      | T1046     |

---

## Skills Demonstrated

* Security Information and Event Management (SIEM)
* Threat Detection and Monitoring
* Detection Engineering
* Incident Investigation
* Threat Hunting
* Windows Security Monitoring
* Linux Security Monitoring
* Sysmon Log Analysis
* MITRE ATT&CK Mapping
* Splunk Dashboard Development
* Alert Creation and Tuning

---

## Project Outcomes

* Centralized log collection
* Multi-source telemetry monitoring
* Custom detection rule development
* Security alert generation
* Threat hunting workflows
* Incident investigation documentation
* SOC analyst skill development

---

## Repository Structure

```text
SOC-Home-Lab-SIEM-Monitoring-Platform
│
├── architecture/
├── dashboards/
├── detections/
├── incident-reports/
├── mitre-attack/
├── screenshots/
└── README.md
```
