# ELK Stack Incident Investigation – Servidae Compromised Workstation

## Overview

This project documents a Security Operations Center (SOC) investigation performed using the ELK Stack (Elasticsearch, Logstash, Kibana).

The objective was to analyze logs collected from a compromised Windows workstation and identify the attacker's actions, techniques, and indicators of compromise (IOCs).

## Tools Used

* Elasticsearch
* Kibana
* Kibana Query Language (KQL)
* Elastic Agent
* MITRE ATT&CK Framework

## Investigation Objectives

* Analyze endpoint log data
* Identify attacker activity
* Detect privilege escalation attempts
* Investigate persistence mechanisms
* Track lateral movement activity
* Map findings to MITRE ATT&CK

## Key Findings

### Initial Access

* Malicious PowerShell script disguised as a PDF document.
* PowerShell executed from the user's Downloads directory.

### Discovery

* Execution of:

  * whoami.exe
  * hostname.exe
  * ipconfig.exe
  * netstat.exe
  * tasklist.exe

### Privilege Escalation

* Attacker downloaded winPEAS for privilege enumeration.
* Registry checks identified AlwaysInstallElevated misconfiguration.
* Malicious MSI installer executed using msiexec.exe.

### Persistence

* Administrative backdoor account created.
* Scheduled task configured for beacon execution.
* Registry Run key modified for persistence.

### Lateral Movement

* Internal payroll application targeted.
* Brute-force authentication attempts observed.
* Sensitive payroll data downloaded.

## MITRE ATT&CK Mapping

| Tactic               | Technique                             |
| -------------------- | ------------------------------------- |
| Initial Access       | Phishing                              |
| Discovery            | System Information Discovery          |
| Privilege Escalation | Exploitation for Privilege Escalation |
| Persistence          | Scheduled Tasks                       |
| Persistence          | Create Account                        |
| Lateral Movement     | Valid Accounts                        |
| Collection           | Data from Information Repositories    |
| Exfiltration         | Exfiltration Over C2 Channel          |

## Skills Demonstrated

* SIEM Investigation
* Log Analysis
* Threat Hunting
* KQL Querying
* IOC Identification
* Incident Response
* MITRE ATT&CK Mapping
* Security Monitoring
