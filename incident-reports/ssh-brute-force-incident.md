# Incident Report: SSH Brute Force Attack

## Summary

Multiple failed SSH authentication attempts were detected against the Ubuntu server. The activity was identified using Linux authentication logs ingested into Splunk Enterprise.

## Detection

```spl
source="/var/log/auth.log" "Failed password"
| stats count by src_ip
| where count > 5
```

## Affected System

* Ubuntu EC2 Server

## Attack Source

* Kali Linux Attack Machine

## Observed Activity

* Multiple failed SSH login attempts
* Repeated authentication failures
* Brute force behavior against SSH service

## MITRE ATT&CK Mapping

* T1110 – Brute Force
* T1110.001 – Password Guessing

## Impact

No successful unauthorized access was observed.

## Response

* Reviewed source IP activity
* Investigated targeted usernames
* Verified system integrity

## Outcome

Attack activity was successfully detected and monitored using Splunk Enterprise.
