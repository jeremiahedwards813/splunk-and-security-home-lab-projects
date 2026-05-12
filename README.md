# Splunk Home Lab

A cybersecurity home lab built to simulate real-world SIEM monitoring using Splunk, Windows event logs, and Linux-based attack and victim machines.

## Skills Demonstrated
- SIEM configuration and log ingestion
- Windows Event Log analysis
- Linux system monitoring
- Network traffic visibility
- Basic threat detection concepts

- ## Lab Architecture

- Kali Linux: attacker machine
- Windows Server: log source (event logs)
- Ubuntu Server: Splunk SIEM instance
- Metasploitable 2: vulnerable target system

# splunk-and-security-home-lab-projects
SIEM home lab using Splunk, Windows Server, Kali Linux, and Metasploitable.
![Lab Topology](screenshots/lab-topology.png)

## Data Flow

Windows Server → Splunk (Ubuntu) → Search & Analysis Dashboard

## Detection Use Case

Detect Windows Security Event logs (WinEventLog:Security) ingested into Splunk and analyzed for authentication and system activity patterns.

## Tools Used
- Splunk Enterprise
- Windows Server
- Kali Linux
- Metasploitable 2
- VMware Fusion

- ## Evidence
- VMware topology screenshot
- Splunk dashboard showing ingested logs

- ## Next Steps
- Build alert rules for brute force detection
- Create dashboards for authentication monitoring
- Expand logging sources (Sysmon, firewall logs)
