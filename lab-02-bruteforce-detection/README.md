# Lab 02: Brute Force Detection Using Splunk

## Overview

This lab focuses on detecting and analyzing brute-force authentication attacks using Splunk as a Security Information and Event Management (SIEM) platform.

The objective of this investigation was to identify suspicious authentication patterns by analyzing login activity, failed authentication attempts, and indicators of attempted unauthorized access.

Brute-force detection is a fundamental SOC analyst skill because attackers frequently attempt to gain access to systems by repeatedly guessing passwords or testing stolen credentials.

---

# Objectives

The goals of this lab were:

* Ingest authentication-related log data into Splunk
* Understand authentication event patterns
* Identify failed login attempts
* Detect potential brute-force activity
* Create searches to identify suspicious behavior
* Analyze attack patterns from log data
* Document findings using a security analyst workflow

---

# Lab Environment

## Tools Used

* Splunk
* Linux authentication logs
* Virtualized security lab environment

## Security Concepts Practiced

* SIEM log analysis
* Authentication monitoring
* Threat detection
* Brute-force investigation
* Security event correlation

---

# Investigation Process

Authentication events were collected and analyzed in Splunk to identify abnormal login behavior.

The investigation focused on:

* Failed authentication attempts
* Source IP addresses
* Target accounts
* Frequency of login failures
* Time-based patterns
* Successful authentication following repeated failures

The goal was to determine whether the observed activity represented normal user behavior or a potential credential attack.

---

# Detection Methodology

A brute-force attack often produces recognizable patterns:

* Many failed login attempts within a short time period
* Attempts against one or multiple accounts
* Repeated activity from the same source
* A successful login after numerous failures

Splunk searches were used to filter authentication events and identify these behaviors.

---

# Findings

The investigation identified authentication activity consistent with a brute-force attack pattern.

Observed indicators included:

* Multiple failed authentication attempts
* Repeated login attempts against user accounts
* Authentication activity occurring within a limited timeframe
* Patterns requiring additional investigation by a security analyst

These findings demonstrate how SIEM tools can identify suspicious authentication behavior and assist analysts during security investigations.

---

# Example Investigation Questions

During analysis, the following questions were considered:

### Who was attempting authentication?

Identified through source IP addresses and usernames contained within authentication events.

### What accounts were targeted?

Reviewed by analyzing usernames associated with failed login attempts.

### Was access successfully obtained?

Reviewed successful authentication events following repeated failures.

### Does the activity represent an attack?

Determined by analyzing frequency, timing, and repetition of authentication attempts.

---

# MITRE ATT&CK Mapping

## Relevant Techniques

| Tactic            | Technique         | ID        | Description                                                                                          |
| ----------------- | ----------------- | --------- | ---------------------------------------------------------------------------------------------------- |
| Credential Access | Brute Force       | T1110     | Attackers may attempt to gain access by repeatedly guessing passwords or authentication credentials. |
| Credential Access | Password Spraying | T1110.003 | Attackers may attempt common passwords against multiple accounts to avoid account lockouts.          |
| Persistence       | Valid Accounts    | T1078     | Attackers may use compromised credentials to maintain access to systems.                             |

---

## ATT&CK Analysis

This lab demonstrates detection of activity associated with credential-based attacks.

By monitoring authentication logs and identifying abnormal login patterns, security analysts can detect behaviors associated with:

* Password guessing attacks
* Password spraying
* Compromised account usage
* Unauthorized access attempts

The detection techniques practiced in this lab align with the Credential Access and Persistence stages of the MITRE ATT&CK framework.

---

# Screenshots and Evidence

Supporting evidence is stored in the following directories:

```text
screenshots/
```

Evidence may include:

* Splunk searches
* Authentication event results
* Detection queries
* Attack pattern analysis

---

# Lessons Learned

This lab demonstrated how SIEM platforms can transform raw authentication logs into actionable security information.

Key takeaways:

* Authentication logs are valuable sources for detecting attacks
* Brute-force activity creates identifiable patterns
* Time-based analysis is important when investigating login events
* Security analysts must understand normal authentication behavior to identify anomalies
* Splunk searches can be used to quickly investigate large amounts of log data

---

# Future Improvements

Possible improvements to this detection include:

* Creating automated Splunk alerts
* Adding IP reputation checks
* Enriching events with threat intelligence
* Creating dashboards for authentication monitoring
* Correlating authentication events with endpoint and network activity

---

# Conclusion

This lab demonstrated the process of detecting brute-force authentication attempts using Splunk.

The investigation showed how SOC analysts use SIEM platforms to monitor authentication activity, identify suspicious behavior, and investigate potential credential attacks.

The skills practiced in this lab are directly applicable to Security Operations Center (SOC) monitoring, incident response, and threat detection workflows.
Lab -02 read me 
