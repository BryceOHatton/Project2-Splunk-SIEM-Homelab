# Homelab Project 1: Splunk SIEM Security Monitoring Lab

## Overview
Built and configured a Splunk SIEM monitoring environment to develop hands-on experience in security monitoring, threat detection, log analysis, and alerting. Configured Splunk Enterprise, Sysmon telemetry collection, Universal Forwarders, dashboards, and real-time alerts to centralize Windows security logs and simulate enterprise SOC monitoring workflows.

## Objectives
- Deploy and configure Splunk Enterprise SIEM
- Configure Sysmon endpoint telemetry collection
- Centralize Windows Security and Sysmon logs
- Configure Splunk Universal Forwarders
- Build SOC-style dashboards and detections
- Create real-time security alerts
- Simulate attack activity to validate detections
- Develop practical SIEM investigation and monitoring skills

## Environment
- Splunk Enterprise (SIEM Server)
- Windows 11 Endpoint Monitoring System
- Kali Linux (Attack Simulation System)
- Sysmon Telemetry Collection
- VMware Workstation

## Architecture Diagram

The diagram below illustrates the Splunk SIEM architecture, endpoint telemetry flow, and centralized log collection process used throughout the lab.

![Architecture Diagram](Diagrams/splunk-siem-architecture.png)

## Key Components
- SPLUNK1 (Splunk Enterprise SIEM Server)
- CLIENT1 (Windows Endpoint Monitoring System)
- KALI1 (Attacker Security Testing Machine)
- Splunk Universal Forwarder
- Sysmon Operational Logging

## Tools Used
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- VMware Workstation
- Windows Event Viewer
- PowerShell
- Windows Defender Firewall
- Kali Linux

## Security Implementation

### SIEM Configuration
- Installed and configured Splunk Enterprise
- Configured Splunk Universal Forwarders for centralized log collection
- Created custom indexes for Sysmon telemetry
- Developed Splunk dashboards and real-time monitoring panels
- Configured centralized Windows Security Event Log ingestion

### Sysmon Telemetry Collection
- Installed Sysmon for advanced endpoint monitoring
- Collected process creation telemetry
- Monitored PowerShell execution activity
- Logged command-line activity and parent-child process relationships
- Monitored endpoint activity through Sysmon Event ID 1 telemetry

### Security Monitoring
- Centralized authentication monitoring
- Created custom Splunk searches for detection visibility
- Configured real-time alerts for suspicious activity
- Developed SOC-style dashboards for security event analysis

## Monitoring and Detection

### Dashboards Created
- Failed Authentication Monitoring
- Account Lockout Monitoring
- PowerShell Execution Monitoring
- Process Creation Monitoring
- Top Executed Processes
- Security Event Volume Monitoring

### Splunk Alerts Configured

| Alert | Severity |
|---|---|
| PowerShell Execution Detection | High |
| Failed Authentication Detection | Medium |
| Account Lockout Detection | High |
| Suspicious Command Shell Activity | Medium |
| Sysmon Process Monitoring | Medium |

### Example Detection Queries

#### Failed Authentication Monitoring

```spl
index=main EventCode=4625
| stats count by Account_Name
```

#### PowerShell Detection

```spl
index=sysmon powershell.exe
```

#### Account Lockout Detection

```spl
index=main EventCode=4740
```

#### Process Creation Monitoring

```spl
index=sysmon "<EventID>1</EventID>"
```

### Key Security Events Analyzed
- 4624 - Successful logon
- 4625 - Failed logon attempt
- 4740 - Account lockout
- Sysmon Event ID 1 - Process creation activity

## MITRE ATT&CK Techniques Simulated

| Technique | Description |
|---|---|
| T1110 | Brute Force Authentication Attempts |
| T1059.001 | PowerShell Execution |
| T1059.003 | Windows Command Shell |
| T1087 | Account Discovery |
| T1078 | Valid Account Activity |

## Attack Simulation

To validate the configured monitoring environment, the following scenarios were performed:
- Simulated repeated failed login attempts to generate authentication events
- Triggered account lockouts through repeated failed authentication attempts
- Executed PowerShell commands to validate telemetry ingestion
- Generated command prompt activity to test process monitoring visibility
- Simulated unauthorized access attempts and reconnaissance activity

Following these events:
- Reviewed logs and telemetry within Splunk SIEM
- Validated Sysmon event ingestion and search visibility
- Verified dashboard updates and alert generation
- Analyzed Windows Security Event Logs and process activity
- Demonstrated basic detection engineering and monitoring workflows

Results:
- Splunk successfully centralized Windows and Sysmon telemetry
- Security events were searchable and visible in dashboards
- Alerts triggered successfully for monitored activity
- Simulated attack activity was logged and validated
- Endpoint telemetry collection functioned as expected

## Validation and Testing

Screenshots are included in the [Screenshots](Screenshots/) directory to show how everything was configured and validated throughout the lab.

Configuration files can be found in the [Configurations](./Configurations) directory.

Splunk search queries are included in the [Queries](./Queries) directory.

### Failed Authentication Monitoring
Failed login attempts monitored through Splunk dashboards.

![Failed Authentication Monitoring](Screenshots/Dashboards/Failed-Authentication-Monitoring.png)

### PowerShell Execution Monitoring
PowerShell execution activity detected through Sysmon telemetry.

![PowerShell Monitoring](Screenshots/Dashboards/PowerShell-Monitoring.png)

### Account Lockout Detection
Account lockout activity detected and monitored through Splunk.

![Account Lockout Detection](Screenshots/Dashboards/Account-Lockout-Monitoring.png)

### Sysmon Process Creation Monitoring
Process creation telemetry analyzed using Sysmon Event ID 1.

![Process Creation Monitoring](Screenshots/Sysmon/Process-Creation-Monitoring.png)

### Splunk Alert Configuration
Real-time Splunk alerts configured for suspicious activity detection.

![Splunk Alerts](Screenshots/Alerts/Splunk-Alert-Configuration.png)

## Repository Structure

```text
/Screenshots
    /Dashboards
    /Alerts
    /Sysmon
    /Splunk-Searches
    /Attack-Simulations

/Queries
    failed-logins.txt
    powershell-detection.txt
    process-creation.txt
    account-lockouts.txt
    sysmon-searches.txt

/Alerts
    splunk-alerts.md

/Configurations
    inputs.conf
    sysmonconfig-export.xml

/Diagrams
    splunk-siem-architecture.png

README.md
```

## Lessons Learned

This project provided practical experience with:
- SIEM deployment and configuration
- Endpoint telemetry collection
- Windows Security Event analysis
- Detection engineering workflows
- Security monitoring and alert validation
- Attack simulation and event investigation

The lab also improved troubleshooting skills related to log ingestion, dashboard development, alert tuning, and Windows event monitoring.

## Key Takeaways
- Configured a centralized SIEM monitoring environment using Splunk Enterprise
- Collected and analyzed Windows Security and Sysmon telemetry
- Developed practical security monitoring and threat detection workflows
- Configured dashboards and alerts for real-time monitoring visibility
- Validated telemetry collection through simulated attack activity
- Gained hands-on experience with Splunk SIEM administration and detection engineering

## Skills Demonstrated

**SIEM & Security Monitoring**
- Splunk Enterprise Administration  
- SIEM Configuration and Monitoring  
- Security Event Monitoring  
- Detection Engineering  

**Endpoint Telemetry**
- Sysmon Configuration  
- Windows Event Log Analysis  
- Process Creation Monitoring  
- PowerShell Activity Monitoring  

**Threat Detection**
- Authentication Monitoring  
- Failed Login Detection  
- Account Lockout Monitoring  
- Suspicious Process Detection  

**Security Operations**
- Security Monitoring and Analysis  
- Alert Configuration and Validation  
- Attack Simulation and Detection Validation  
- Basic Incident Detection and Investigation  

## Future Improvements
Planned future enhancements for the lab include:
- Microsoft Sentinel integration
- Cloud SIEM monitoring
- Vulnerability management with Nessus
- Additional Sysmon detection tuning
- Expanded attack simulation scenarios
- Threat hunting dashboards

## Project Status
in-Progress - Splunk SIEM environment deployed, telemetry collection configured, dashboards and alerts implemented, and monitoring functionality validated through simulated attack activity and event analysis.
