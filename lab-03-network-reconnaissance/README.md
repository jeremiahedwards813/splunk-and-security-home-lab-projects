# Lab 03: Network Reconnaissance and Service Discovery

## Overview

This lab focuses on network reconnaissance, the process of gathering information about systems, hosts, and services within a network environment.

The objective of this exercise was to identify exposed network services, open ports, and available information about a target system using reconnaissance techniques commonly used by both security professionals and attackers.

Understanding reconnaissance activity is important for defenders because many attacks begin with information gathering before exploitation attempts occur.

---

# Objectives

The goals of this lab were:

* Perform network discovery against a target system
* Identify open ports and running services
* Understand how reconnaissance reveals attack surface information
* Analyze scan results from a security perspective
* Document findings using a security analyst workflow

---

# Lab Environment

## Tools Used

* Nmap
* Kali Linux
* Virtualized security lab environment

## Security Concepts Practiced

* Network discovery
* Port scanning
* Service enumeration
* Attack surface identification
* Reconnaissance analysis

---

# Reconnaissance Process

Network reconnaissance was performed against a target system to gather information about available services and potential entry points.

The investigation focused on identifying:

* Active hosts
* Open ports
* Running services
* Service versions
* Potential security risks

The information collected during reconnaissance can help security teams understand exposed systems and identify areas that may require additional protection.

---

# Scan Activities

The reconnaissance process included scanning the target system to identify available network services.

The analysis reviewed:

* Open TCP ports
* Associated services
* Potential attack vectors
* Unexpected exposed services

Open ports do not automatically indicate a vulnerability, but they represent potential communication paths that should be understood and properly secured.

---

# Findings

The scan identified network services exposed on the target system.

Key observations included:

* Accessible ports were identified
* Services responding to network requests were discovered
* The exposed attack surface was documented
* Results demonstrated how reconnaissance can reveal information about a target environment

From a defensive perspective, this information can be used to:

* Reduce unnecessary exposed services
* Verify firewall configurations
* Identify unauthorized services
* Improve network security posture

---

# Security Analysis

Reconnaissance activity is often performed before an attack to gather information about a target.

Attackers may use scanning techniques to determine:

* What systems exist
* What services are available
* Which technologies are running
* Where potential weaknesses may exist

Security teams can use the same information defensively to identify and reduce unnecessary exposure.

---

# MITRE ATT&CK Mapping

## Relevant Techniques

| Tactic    | Technique                              | ID    | Description                                                                                       |
| --------- | -------------------------------------- | ----- | ------------------------------------------------------------------------------------------------- |
| Discovery | Network Service Scanning               | T1046 | Attackers may scan systems to identify open ports, services, and network-accessible applications. |
| Discovery | System Network Configuration Discovery | T1016 | Attackers may gather information about network configurations and connectivity.                   |
| Discovery | Remote System Discovery                | T1018 | Attackers may identify additional systems within a network environment.                           |

---

## ATT&CK Analysis

This lab aligns with the Discovery phase of the MITRE ATT&CK framework.

Network reconnaissance allows attackers to gather information needed for later stages of an attack. From a defensive perspective, detecting unusual scanning activity can help identify early indicators of compromise.

Security monitoring solutions may detect reconnaissance through:

* Large numbers of connection attempts
* Sequential port scanning behavior
* Unusual internal network discovery activity
* Scanning from unauthorized hosts

---

# Screenshots and Evidence

Supporting evidence is stored in:

```text
screenshots/
```

Evidence may include:

* Nmap scan results
* Identified open ports
* Service enumeration results
* Network discovery findings

---

# Lessons Learned

This lab demonstrated how reconnaissance techniques reveal information about network environments.

Key takeaways:

* Open ports represent potential communication paths into systems
* Network visibility is important for security monitoring
* Reconnaissance is often the first stage of an attack
* Understanding attacker techniques helps defenders build better detection strategies
* Security teams can use reconnaissance techniques to identify and reduce their own attack surface

---

# Future Improvements

Possible improvements to this lab include:

* Comparing scan results before and after firewall changes
* Detecting reconnaissance activity using a SIEM platform
* Creating alerts for suspicious scanning behavior
* Mapping additional scan techniques to MITRE ATT&CK
* Analyzing reconnaissance traffic using Wireshark

---

# Conclusion

This lab demonstrated the process of performing network reconnaissance and analyzing exposed services within a target environment.

The skills practiced in this exercise are directly applicable to vulnerability assessment, SOC monitoring, threat detection, and incident response workflows.

Understanding reconnaissance techniques allows defenders to recognize early attack activity and better protect network environments.

