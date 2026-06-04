# PowerShell Execution Detection

## Objective

Detect PowerShell execution activity on Windows endpoints using Sysmon Event ID 1 (Process Creation).

## Log Source

* Sysmon Operational Logs
* Event ID: 1 (Process Creation)

## Detection Query

```spl
index=main sourcetype=WinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=1 Image="*powershell.exe"
```

## Detection Logic

This query identifies instances where PowerShell is launched on the monitored Windows endpoint. PowerShell is frequently used by administrators for legitimate purposes but is also heavily abused by attackers for:

* Initial access
* Malware execution
* Privilege escalation
* Lateral movement
* Defense evasion

Monitoring PowerShell activity is a critical component of endpoint threat detection.

## Investigation Steps

1. Review the process path.
2. Identify the user account executing PowerShell.
3. Examine parent-child process relationships.
4. Inspect command-line arguments.
5. Determine whether execution was authorized.

## Severity

Medium

## MITRE ATT&CK Mapping

* T1059.001 – PowerShell
* T1059 – Command and Scripting Interpreter

## Outcome

Successfully detected PowerShell execution events using Sysmon logs forwarded to Splunk Enterprise.
