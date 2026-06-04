# Dashboard Documentation

## Windows Monitoring Dashboard

The Windows Monitoring Dashboard provides visibility into endpoint activity collected through Sysmon and Windows Security Logs.

### Top Executed Processes

Displays the most frequently executed processes observed through Sysmon Event ID 1 (Process Creation). This panel helps identify commonly used applications and potentially suspicious process activity.

### Process Creation Trend

Visualizes process creation activity over time. Sudden spikes may indicate malicious execution, scripting activity, or abnormal user behavior.

### PowerShell Activity Trend

Tracks PowerShell execution activity across the monitored Windows endpoint. PowerShell is frequently leveraged by attackers and administrators alike, making continuous monitoring important.

### Top Destination Ports

Displays outbound network communication destinations observed through Sysmon Event ID 3 (Network Connections). Useful for identifying unusual network activity.

---

## Linux Monitoring Dashboard

The Linux Monitoring Dashboard focuses on SSH authentication activity collected from Ubuntu authentication logs.

### Top Attacker IP Addresses

Displays source IP addresses responsible for failed SSH authentication attempts.

### SSH Attack Timeline

Visualizes failed SSH login attempts over time and helps identify brute force attack patterns.

### Failed Authentication Monitoring

Tracks authentication failures across the monitored Linux server to support threat hunting and incident investigation.

---

## Outcome

The dashboards provide centralized visibility into Windows and Linux security events, enabling proactive monitoring, detection, and investigation workflows.
