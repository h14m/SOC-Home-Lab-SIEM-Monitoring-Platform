# SSH Brute Force Detection

## Objective

Detect multiple failed SSH login attempts against the Ubuntu server indicating a potential brute force attack.

## Log Source

* Linux Authentication Logs
* File: /var/log/auth.log

## Detection Query

```spl
source="/var/log/auth.log" "Failed password"
| stats count by src_ip
| where count > 5
```

## Detection Logic

This detection identifies repeated failed SSH authentication attempts originating from the same source IP address. Such activity is commonly associated with:

* Password guessing attacks
* Credential stuffing
* Automated brute force tools
* Unauthorized access attempts

## Investigation Steps

1. Identify the source IP address.
2. Review the number of failed login attempts.
3. Determine targeted usernames.
4. Check for successful logins following failures.
5. Assess whether the source is internal or external.

## Severity

High

## MITRE ATT&CK Mapping

* T1110 – Brute Force
* T1110.001 – Password Guessing

## Outcome

Successfully detected SSH brute force activity generated from the Kali Linux attack machine against the Ubuntu server and visualized the events in Splunk Enterprise.
