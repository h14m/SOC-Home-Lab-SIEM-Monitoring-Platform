# Incident Report: External Network Connection Activity

## Summary

Outbound network connections were detected using Sysmon Event ID 3 network connection logs.

## Detection

```spl
index=main sourcetype=WinEventLog:Microsoft-Windows-Sysmon/Operational EventCode=3
DestinationIp!="127.0.0.1"
```

## Affected System

* Windows VM

## Observed Activity

* HTTPS communication over port 443
* Splunk Universal Forwarder communication over port 9997
* Normal outbound application traffic

## MITRE ATT&CK Mapping

* T1071 – Application Layer Protocol
* T1049 – System Network Connections Discovery

## Impact

No malicious outbound communication was identified.

## Response

* Reviewed destination IP addresses
* Validated destination ports
* Confirmed expected network activity

## Outcome

Network activity monitoring was successfully implemented using Sysmon and Splunk Enterprise.
