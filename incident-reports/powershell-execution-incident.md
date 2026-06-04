# Incident Report: PowerShell Execution Activity

## Summary

PowerShell execution activity was detected on the Windows endpoint through Sysmon Event ID 1 process creation logs.

## Detection

```spl
index=main sourcetype=WinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=1 Image="*powershell.exe"
```

## Affected System

* Windows VM

## Observed Activity

* PowerShell process execution
* Command-line interpreter activity
* Administrative scripting activity

## MITRE ATT&CK Mapping

* T1059.001 – PowerShell

## Impact

No malicious behavior was confirmed during analysis. Activity was generated as part of controlled lab testing.

## Response

* Reviewed PowerShell execution events
* Verified process activity
* Confirmed authorized execution

## Outcome

PowerShell activity was successfully detected and visualized within Splunk Enterprise.
