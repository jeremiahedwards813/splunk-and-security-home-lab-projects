
# Lab 6: Endpoint Threat Hunting with Sysmon

## Overview

This lab demonstrates endpoint threat hunting using Microsoft Sysmon telemetry. Sysmon was installed on a Windows endpoint to collect detailed process creation data and provide visibility beyond standard Windows event logging.

The investigation focused on analyzing process execution chains, command-line arguments, and parent-child relationships to identify potentially suspicious activity.

---

## Objectives

* Install and configure Sysmon on a Windows endpoint
* Generate and analyze Sysmon Event ID 1 process creation logs
* Investigate PowerShell execution behavior
* Identify suspicious command-line indicators
* Analyze parent-child process relationships
* Document findings using a SOC analyst workflow

---

## Lab Environment

| System            | Purpose                            |
| ----------------- | ---------------------------------- |
| Windows VM        | Endpoint monitored with Sysmon     |
| Kali Linux VM     | Security testing environment       |
| GitHub Repository | Documentation and evidence storage |

---

## Tools Used

* Microsoft Sysmon
* Windows Event Viewer
* PowerShell
* GitHub

---

# Investigation Process

## 1. Sysmon Installation

Sysmon was installed as a Windows service using a custom XML configuration file.

The configuration enabled monitoring of:

* Process creation events
* Network connections

Configuration file:

```
evidence/configs/sysmon-config.xml
```

---

## 2. Sysmon Verification

After installation, Sysmon was verified by reviewing:

```
Applications and Services Logs
└── Microsoft
    └── Windows
        └── Sysmon
            └── Operational
```

Sysmon Event ID 1 was used throughout the investigation.

Event ID 1 records:

* Process image
* Command-line arguments
* User account
* Parent process

---

## 3. Baseline Process Monitoring

Normal system activity was reviewed to establish a baseline of endpoint behavior.

Sysmon Event ID 1 demonstrated how process creation telemetry can reveal:

* What executable was launched
* How it was launched
* Which process started it

---

## 4. Normal PowerShell Investigation

A controlled PowerShell execution was generated and analyzed.

Example command:

```
powershell.exe -NoProfile -Command "Get-Process"
```

Observed process relationship:

```
cmd.exe
 |
 └── powershell.exe
```

Analysis:

The PowerShell command retrieved running processes. This behavior is commonly used by administrators but can also be used by attackers for system discovery.

The event was investigated by reviewing:

* Image
* CommandLine
* ParentImage

---

## 5. Suspicious PowerShell Investigation

A second PowerShell event was generated to simulate activity that may require additional investigation.

Command:

```
powershell -ExecutionPolicy Bypass
```

Observed process relationship:

```
powershell.exe
 |
 └── powershell.exe -ExecutionPolicy Bypass
```

Analysis:

The use of `ExecutionPolicy Bypass` is commonly reviewed during security investigations because attackers may use it to avoid PowerShell execution restrictions.

In this lab, the command was intentionally generated for detection practice and was not malicious.

---

# Findings

## Finding 1: Improved Endpoint Visibility

Sysmon provided additional visibility into endpoint activity beyond default Windows logging.

The telemetry allowed investigation of:

* Process creation
* Execution chains
* Command-line activity

---

## Finding 2: Process Relationships Provide Context

Parent-child process relationships helped determine how activity was initiated.

Example:

```
cmd.exe → powershell.exe
```

Understanding these relationships helps analysts distinguish normal administrative activity from potentially suspicious behavior.

---

## Finding 3: PowerShell Requires Context

PowerShell is commonly used by both administrators and attackers.

A PowerShell event alone does not indicate malicious activity. Analysts must evaluate:

* Command-line arguments
* Parent processes
* User activity
* System context

---

# MITRE ATT&CK Mapping

## T1059.001 - Command and Scripting Interpreter: PowerShell

PowerShell execution was monitored using Sysmon Event ID 1.

Reference:

https://attack.mitre.org/techniques/T1059/001/

---

## T1059 - Command and Scripting Interpreter

Command execution activity was analyzed through endpoint process telemetry.

Reference:

https://attack.mitre.org/techniques/T1059/

---

# Evidence

## Screenshots

Location:

```
evidence/screenshots/
```

Included evidence:

* Sysmon process creation baseline
* Normal PowerShell investigation
* Suspicious PowerShell investigation

---

## Event Logs

Location:

```
evidence/logs/
```

Included:

```
sysmon-operational.evtx
```

---

## Configuration

Location:

```
evidence/configs/
```

Included:

```
sysmon-config.xml
```

---

# Lessons Learned

* Endpoint telemetry is critical for security investigations.
* Sysmon provides valuable visibility into process execution.
* Command-line arguments provide important investigative context.
* Parent-child process relationships help identify suspicious behavior.
* PowerShell activity requires analysis and context rather than automatic classification as malicious.

---

# Conclusion

This lab demonstrated a basic endpoint threat hunting workflow using Microsoft Sysmon.

By collecting process creation telemetry and analyzing execution behavior, security analysts can identify suspicious activity, investigate potential threats, and document findings using a structured SOC workflow.



