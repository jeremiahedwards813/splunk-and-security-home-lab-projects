# Lab 05 – Windows Incident Response Investigation

## Objective

The objective of this lab was to simulate the initial stages of a Windows incident response investigation by collecting baseline system information, preserving event logs, documenting evidence, and analyzing PowerShell activity. The focus was on following a structured evidence collection process while maintaining the integrity of collected artifacts.

---

## Lab Environment

| Component        | Description                 |
| ---------------- | --------------------------- |
| Host             | macOS                       |
| Virtualization   | VMware Fusion               |
| Target VM        | Windows                     |
| Analysis VM      | Kali Linux                  |
| Evidence Storage | GitHub Portfolio Repository |

---

## Tools Used

* Windows Event Viewer
* Windows PowerShell
* Local Group Policy Editor
* VMware Fusion Shared Folders
* GitHub Web Interface

---

## Investigation Overview

The investigation followed a standard evidence collection workflow commonly used during the early stages of an incident response engagement.

Activities performed included:

* Collected baseline Windows system information.
* Exported the Windows Security Event Log.
* Reviewed the Windows Security log for investigative artifacts.
* Examined the PowerShell Operational log.
* Identified PowerShell Script Block Logging events (Event ID 4104).
* Exported relevant PowerShell event logs for preservation.
* Captured screenshots documenting the investigation process.
* Enabled additional PowerShell logging policies to improve future forensic visibility.

---

## Evidence Collected

### System Information

* windows-baseline.txt

### Event Logs

* Security-baseline.evtx
* PowerShell-ScriptBlock-Events.evtx

### Screenshots

* Event Viewer Security Log Overview
* PowerShell Commands
* System Information Output
* PowerShell Script Block Events

---

## Findings

During the investigation, Windows event logs were reviewed to establish a baseline and identify PowerShell-related activity.

PowerShell Operational logging contained script block events that were preserved for later analysis. While the initial commands executed during testing were not fully captured due to logging configuration, additional PowerShell logging policies were enabled to improve future visibility and investigative capabilities.

The investigation demonstrates the importance of:

* Collecting evidence before making system changes.
* Preserving original event logs.
* Documenting investigative actions.
* Improving logging configuration for future incident response efforts.

---

## MITRE ATT&CK Mapping

| ATT&CK Technique                                    | ID        | Reason                                                                                   |
| --------------------------------------------------- | --------- | ---------------------------------------------------------------------------------------- |
| PowerShell                                          | T1059.001 | Investigated PowerShell execution activity.                                              |
| Indicator Removal (Evidence Preservation Awareness) | T1070     | Demonstrated evidence preservation by exporting original event logs before modification. |
| System Information Discovery                        | T1082     | Collected baseline operating system information.                                         |
| System Owner/User Discovery                         | T1033     | Verified user context during investigation.                                              |

---

## Skills Demonstrated

* Windows Incident Response
* Event Log Analysis
* Evidence Preservation
* PowerShell Investigation
* Windows Event Viewer
* MITRE ATT&CK Mapping
* Digital Forensics Fundamentals
* Documentation
* GitHub Portfolio Management

---

## Repository Structure

```text
lab-05-incident-response-investigation/
│
├── README.md
│
└── evidence/
    ├── logs/
    │   ├── Security-baseline.evtx
    │   └── PowerShell-ScriptBlock-Events.evtx
    │
    ├── screenshots/
    │   ├── event-viewer-security-log-overview.png
    │   ├── powershell-commands.png
    │   ├── systeminfo-output.png
    │   └── powershell-script-block-events.png
    │
    └── system-info/
        └── windows-baseline.txt
```

---

## Lessons Learned

This lab reinforced the importance of collecting and preserving forensic evidence before making investigative changes to a system. It also demonstrated that proper logging configuration is essential for effective incident response. Future labs will build on this foundation by generating controlled attack activity and validating detection using enhanced Windows auditing and PowerShell logging.

