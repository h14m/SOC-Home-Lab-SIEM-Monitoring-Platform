# Command Prompt Execution Detection

## Objective

Detect Command Prompt (cmd.exe) execution on Windows endpoints using Sysmon process creation events.

## Log Source

* Sysmon Operational Logs
* Event ID: 1 (Process Creation)

## Detection Query

```spl
index=main sourcetype=WinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=1 Image="*cmd.exe"
```

## Detection Logic

This detection identifies execution of the Windows Command Prompt. Attackers frequently use cmd.exe to execute system commands, run scripts, perform reconnaissance, and launch additional tools.

## Investigation Steps

1. Review the user account associated with the process.
2. Examine parent-child process relationships.
3. Verify whether execution was expected.
4. Investigate related processes launched from cmd.exe.

## Severity

Medium

## MITRE ATT&CK Mapping

* T1059.003 – Windows Command Shell

## Outcome

Successfully detected Command Prompt execution events using Sysmon logs forwarded to Splunk Enterprise.
