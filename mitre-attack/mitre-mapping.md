# MITRE ATT&CK Mapping

## Overview

This SOC Home Lab uses Windows Sysmon logs, Windows Security Logs, Linux SSH logs, and Splunk Enterprise to detect and monitor adversary behavior. The following table maps implemented detections to MITRE ATT&CK techniques.

| Detection                             | MITRE Technique ID | Technique Name                       |
| ------------------------------------- | ------------------ | ------------------------------------ |
| SSH Brute Force Detection             | T1110              | Brute Force                          |
| SSH Password Guessing                 | T1110.001          | Password Guessing                    |
| PowerShell Execution Detection        | T1059.001          | PowerShell                           |
| CMD Execution Detection               | T1059.003          | Windows Command Shell                |
| External Network Connection Detection | T1071              | Application Layer Protocol           |
| External Network Connection Detection | T1049              | System Network Connections Discovery |
| Nmap Reconnaissance Activity          | T1046              | Network Service Discovery            |

## Attack Simulations Performed

### SSH Brute Force

* Attack Source: Kali Linux
* Target: Ubuntu EC2 Server
* Detection Source: Linux Authentication Logs
* Technique: T1110

### PowerShell Activity

* Attack Source: Windows Endpoint
* Detection Source: Sysmon Event ID 1
* Technique: T1059.001

### Command Shell Activity

* Attack Source: Windows Endpoint
* Detection Source: Sysmon Event ID 1
* Technique: T1059.003

### Network Connection Monitoring

* Detection Source: Sysmon Event ID 3
* Techniques: T1071, T1049

### Nmap Reconnaissance

* Attack Source: Kali Linux
* Target: Windows VM
* Observation: Firewall filtered scan traffic
* Technique: T1046

## Outcome

This SOC Home Lab demonstrates detection engineering, SIEM monitoring, threat hunting, attack simulation, and MITRE ATT&CK mapping using Splunk Enterprise.
