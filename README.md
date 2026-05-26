# Homelab Project 2: Splunk SIEM Security Monitoring Lab

## Overview
Built and configured a Splunk SIEM monitoring environment to develop hands-on experience in security monitoring, threat detection, log analysis, and alerting. Configured Splunk Enterprise, Sysmon telemetry collection, and Universal Forwarders to centralize Windows security logs and simulate enterprise SOC monitoring workflows.

Implemented custom searches, dashboards, and alerts to monitor authentication activity, PowerShell execution, process creation events, and network discovery activity. Validated detections through controlled attack simulations and real-time event analysis.

---

# Environment
- Splunk Enterprise 9.4.2
- Windows 11 Endpoint Monitoring System
- Kali Linux Attack Simulation System
- Sysmon Telemetry Collection
- Splunk Universal Forwarder
- VMware Workstation

---

# Key Components
- SPLUNK1 (Splunk Enterprise SIEM Server)
- CLIENT1 (Windows Endpoint Monitoring System)
- KALI1 (Attack Simulation System)
- Sysmon Endpoint Telemetry
- Splunk Search & Reporting Application
- SOC Monitoring Dashboard
- Real-Time Detection Alerts

---

# Security Implementation

## SIEM Deployment
- Installed and configured Splunk Enterprise
- Configured centralized log ingestion from Windows systems
- Deployed Splunk Universal Forwarder on monitored endpoints
- Validated telemetry ingestion into Splunk indexes

## Sysmon Telemetry Collection
- Installed Sysmon endpoint monitoring
- Configured Sysmon operational logging
- Monitored process creation activity
- Collected PowerShell execution telemetry
- Captured command-line process activity
- Centralized Sysmon telemetry within Splunk

## Detection Engineering
Created custom Splunk searches and real-time alerts for:

- Failed authentication attempts
- PowerShell execution activity
- Command shell execution
- Network discovery and reconnaissance activity
- Process creation monitoring

## SOC Dashboard Development
Built a centralized SOC-style monitoring dashboard to visualize:
- Total security event activity
- Process creation trends
- PowerShell execution monitoring
- Failed login activity
- Network discovery activity
- Real-time event monitoring

---

# Monitoring and Detection

## Security Monitoring Searches

### Failed Authentication Monitoring
```spl
index=main EventCode=4625
```

### PowerShell Execution Detection
```spl
index=sysmon powershell.exe
```

### Command Execution Monitoring
```spl
index=sysmon cmd.exe
```

### Network Discovery Activity
```spl
index=sysmon ping.exe OR nslookup.exe
```

### Sysmon Telemetry Monitoring
```spl
index=sysmon
```

---

# Real-Time Alerts Configured

| Alert Name | Severity | Purpose |
|---|---|---|
| Failed Authentication Detection | High | Detect repeated failed login attempts |
| PowerShell Execution Detection | Medium | Monitor suspicious PowerShell execution |
| Suspicious Command Shell Activity | Medium | Detect command shell execution activity |
| Network Discovery Activity | Medium | Detect reconnaissance-related commands |
| Account Lockout Detection | High | Detect account lockout activity |

---

# Attack Simulation

To validate the configured detections and monitoring capabilities, the following simulations were performed:

- Executed PowerShell commands to generate Sysmon telemetry
- Performed failed login attempts to trigger authentication monitoring
- Executed command shell activity using cmd.exe
- Performed network discovery activity using ping and nslookup
- Generated process creation events to validate telemetry collection
- Triggered real-time alerts within Splunk

Results:
- Security telemetry was successfully ingested into Splunk
- Real-time alerts triggered as expected
- Dashboard visualizations updated dynamically
- PowerShell and command execution activity was detected
- Failed login activity was logged and searchable
- Network discovery activity was successfully monitored

---

# Validation and Testing

Screenshots are included in the [Screenshots](Screenshots/) directory to demonstrate deployment, telemetry ingestion, monitoring, alerting, and dashboard functionality throughout the lab.

Configuration files can be found in the [Configurations](Configurations/) directory.

Custom Splunk searches are included in the [Queries](Queries/) directory.

---

# Dashboard Monitoring

## SOC Monitoring Dashboard
Centralized SOC dashboard displaying overall security monitoring activity.

![SOC Dashboard](Screenshots/Dashboards/SOC-Monitoring-Dashboard-1.png)

---

## Process Creation Activity Monitoring
Real-time visualization of process creation telemetry.

![Process Monitoring](Screenshots/Sysmon/Process-Creation-Monitoring.png)

---

## PowerShell Execution Monitoring
PowerShell execution telemetry monitored through Sysmon logs.

![PowerShell Detection](Screenshots/Sysmon/Powershell-Detection-Search.png)

---

## Network Discovery Detection
Detection of reconnaissance-related commands such as nslookup and ping.

![Network Discovery](Screenshots/Alerts/Network-Discovery-Detection.png)

---

## Failed Login Activity
Failed authentication attempts successfully detected and monitored.

![Failed Logins](Screenshots/Attack-Simulations/Failed-Login-Simulation.png)

---

## Triggered Real-Time Alerts
Real-time alerts triggered through configured Splunk detections.

![Triggered Alerts](Screenshots/Alerts/Triggered-Alerts.png)

---

## Universal Forwarder Log Ingestion
Validation of Sysmon telemetry ingestion through the Splunk Universal Forwarder.

![Log Ingestion](Screenshots/Ingestion/Universal-Forwarder-Ingestion.png)

---

# Key Takeaways
- Deployed and configured a functional Splunk SIEM environment
- Centralized Windows Security and Sysmon telemetry
- Developed practical experience with SIEM log analysis and monitoring
- Built SOC-style dashboards and visualizations
- Created custom Splunk detections and real-time alerts
- Simulated attack activity to validate monitoring capabilities
- Gained hands-on experience with endpoint telemetry collection
- Performed event analysis using Splunk Search Processing Language (SPL)

---

# Skills Demonstrated

## SIEM & Security Monitoring
- Splunk Enterprise Administration
- Security Information and Event Management (SIEM)
- Security Event Monitoring
- Log Aggregation and Analysis
- Security Dashboard Development

## Detection Engineering
- Splunk Search Processing Language (SPL)
- Real-Time Alert Development
- Threat Detection
- Authentication Monitoring
- Process Execution Monitoring

## Endpoint Telemetry
- Sysmon Configuration and Monitoring
- Windows Event Log Analysis
- PowerShell Activity Monitoring
- Process Creation Monitoring
- Command-Line Auditing

## Incident Detection & Analysis
- Threat Hunting
- Security Event Investigation
- Alert Triage
- Attack Simulation Validation
- Security Monitoring Workflows

---

# Project Status
Completed — Splunk SIEM environment successfully deployed, telemetry centralized, detections configured, dashboards created, and monitoring functionality validated through simulated attack activity and real-time alerting.
