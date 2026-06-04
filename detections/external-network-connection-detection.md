# External Network Connection Detection

## Objective

Detect outbound network connections initiated by processes on the Windows endpoint using Sysmon Event ID 3.

## Log Source

* Sysmon Operational Logs
* Event ID: 3 (Network Connection)

## Detection Query

```spl
index=main sourcetype=WinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=3
DestinationIp!="127.0.0.1"
```

## Detection Logic

This detection identifies outbound network connections established by processes running on the Windows endpoint. Monitoring external connections helps identify:

* Command and Control (C2) communication
* Data exfiltration attempts
* Unauthorized remote access
* Suspicious internet activity

## Investigation Steps

1. Identify the process initiating the connection.
2. Review destination IP addresses and ports.
3. Determine whether the destination is trusted.
4. Correlate with process creation events.
5. Investigate unusual communication patterns.

## Severity

Medium

## MITRE ATT&CK Mapping

* T1071 – Application Layer Protocol
* T1049 – System Network Connections Discovery

## Outcome

Successfully monitored outbound network connections using Sysmon Event ID 3 and visualized network activity in Splunk Enterprise.
