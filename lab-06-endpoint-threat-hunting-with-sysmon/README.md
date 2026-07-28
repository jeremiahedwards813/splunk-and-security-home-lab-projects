
# Lab 6: Endpoint Threat Hunting with Sysmon

## Overview

This lab demonstrates endpoint threat hunting using Microsoft Sysmon telemetry. Sysmon was installed on a Windows endpoint to collect detailed process creation data and provide visibility beyond standard Windows event logging.

The investigation focused on analyzing process execution chains, command-line arguments, and parent-child relationships to identify potentially suspicious activity.

---

## Objectives

- Install and configure Sysmon on a Windows endpoint
- Generate and analyze Sysmon Event ID 1 process creation logs
- Investigate PowerShell execution behavior
- Identify suspicious command-line indicators
- Analyze parent-child process relationships
- Document findings using a SOC analyst workflow

---

## Lab Environment

| System | Purpose |
|---|---|
| Windows VM | Endpoint monitored with Sysmon |
| Kali Linux VM | Security testing environment |
| GitHub Repository | Documentation and evidence storage |

---

## Tools Used

- Microsoft Sysmon
- Windows Event Viewer
- PowerShell
- GitHub

---

# Investigation Process

## 1. Sysmon Installation

Sysmon was installed as a Windows service using a custom XML configuration file.

The configuration enabled monitoring of:

- Process creation events
- Network connections

Evidence:
