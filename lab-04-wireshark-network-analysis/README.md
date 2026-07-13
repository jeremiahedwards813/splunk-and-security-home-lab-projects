# Lab 04: Network Traffic Analysis Using Wireshark

## Overview

This lab focuses on analyzing network traffic using Wireshark, a packet analysis tool used by security professionals to inspect communications between systems.

The objective of this exercise was to capture and analyze network traffic, understand common network protocols, and develop the ability to identify important information within packet captures.

Network traffic analysis is a critical SOC analyst skill because investigating suspicious communications often begins with understanding normal network behavior and identifying deviations from that baseline.

---

# Objectives

The goals of this lab were:

* Capture network traffic using Wireshark
* Analyze packet-level network communication
* Understand TCP connection establishment
* Examine DNS queries and responses
* Identify source and destination communication patterns
* Understand how packet captures support security investigations
* Document network analysis findings

---

# Lab Environment

## Tools Used

* Wireshark
* Kali Linux
* Virtualized security lab environment

## Protocols Analyzed

* DNS
* TCP
* Ethernet
* IP
* HTTPS-related network communication

---

# Capture Process

Network traffic was captured while performing normal web activity.

The capture was analyzed to identify:

* Source and destination IP addresses
* DNS resolution activity
* TCP connection establishment
* Packet flags
* Communication patterns

The goal was to understand how systems communicate across a network and how analysts use packet captures during investigations.

---

# Analysis Performed

## DNS Analysis

DNS traffic was reviewed to understand how domain names are translated into IP addresses.

The investigation examined:

* DNS queries
* DNS responses
* Resolved IP addresses
* Associated communication flow

DNS analysis is valuable during security investigations because malicious activity may use DNS for:

* Command and control communication
* Data exfiltration
* Domain-based indicators of compromise

---

## TCP Connection Analysis

TCP packets were examined to understand the connection process between systems.

The analysis included:

* SYN packets
* SYN/ACK responses
* ACK packets
* Connection establishment sequence

Understanding normal TCP behavior helps analysts identify abnormal communication patterns during investigations.

---

# Findings

The packet capture demonstrated normal network communication behavior.

Observed activity included:

* DNS queries and responses
* Successful TCP connection establishment
* Communication between local and remote systems
* Standard web browsing traffic patterns

No malicious activity was identified within this capture.

The analysis provided a baseline understanding of normal network behavior that can be used for comparison during future investigations involving suspicious traffic.

---

# Security Analysis

Packet captures provide valuable evidence during security investigations.

Security analysts may use Wireshark to investigate:

* Suspicious outbound connections
* Malware command-and-control traffic
* Data exfiltration attempts
* Unusual DNS activity
* Unauthorized communication

Understanding normal traffic patterns is essential because effective detection requires knowing what abnormal behavior looks like.

---

# MITRE ATT&CK Mapping

## Relevant Techniques

| Tactic              | Technique                  | ID    | Description                                                                            |
| ------------------- | -------------------------- | ----- | -------------------------------------------------------------------------------------- |
| Discovery           | Network Service Scanning   | T1046 | Attackers may scan network services to identify available systems and services.        |
| Command and Control | Application Layer Protocol | T1071 | Attackers may use common network protocols for communication with compromised systems. |

---

## ATT&CK Analysis

This lab did not simulate a malicious attack and did not identify confirmed ATT&CK techniques within the captured traffic.

However, the skills practiced support detection and investigation of ATT&CK-related activity.

Wireshark analysis can assist defenders in identifying behaviors associated with techniques such as:

* T1071 – Application Layer Protocol

  * Malicious actors may use protocols such as HTTP, HTTPS, DNS, or other application-layer communications for command and control.

* T1046 – Network Service Scanning

  * Reconnaissance activity may be identified through unusual network connection attempts and scanning behavior.

Future malicious traffic analysis labs can use these same skills to identify confirmed ATT&CK techniques.

---

# Screenshots and Evidence

Supporting evidence is stored in:

```text
screenshots/
```

Evidence includes:

* Packet capture overview
* DNS query analysis
* TCP SYN/SYN-ACK analysis
* Network communication details

Packet captures are stored in:

```text
pcaps/
```

Included files:

* `web-connection-sequence.pcapng`
* `web-browsing.pcapng`

---

# Lessons Learned

This lab demonstrated the importance of packet-level visibility during security investigations.

Key takeaways:

* Wireshark provides detailed visibility into network communication
* DNS analysis can reveal important investigation information
* TCP connection behavior provides insight into communication patterns
* Packet captures can provide evidence during incident response investigations
* Understanding normal traffic is necessary for identifying malicious activity

---

# Future Improvements

Possible improvements to this lab include:

* Analyze a known malicious PCAP
* Identify command-and-control traffic
* Investigate suspicious DNS behavior
* Detect scanning activity in packet captures
* Compare normal and malicious network behavior
* Create detection rules based on observed traffic

---

# Conclusion

This lab demonstrated how security analysts use Wireshark to capture and analyze network traffic.

The skills developed in this exercise provide a foundation for investigating suspicious communications, identifying indicators of compromise, and supporting incident response activities.

Network traffic analysis is a core SOC analyst skill and is directly applicable to threat hunting, detection engineering, and digital forensics workflows.
