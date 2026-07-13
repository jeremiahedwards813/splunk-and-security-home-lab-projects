## MITRE ATT&CK Mapping

| Tactic | Technique | ID | Description |
|---|---|---|---|
| Example | Example Technique | T0000 | Explanation |# Lab 01: Authentication Monitoring

## Overview

This lab focuses on monitoring and analyzing authentication activity to identify suspicious login behavior. The goal was to understand how security analysts use authentication logs to detect potential account compromise, brute-force attempts, and abnormal access patterns.

Authentication monitoring is a fundamental SOC analyst skill because compromised credentials are one of the most common methods attackers use to gain access to systems.

---

## Objectives

* Understand authentication event data and why it is important for security monitoring
* Identify successful and failed login attempts
* Detect suspicious authentication patterns
* Analyze login activity for signs of unauthorized access
* Document findings using a security analyst workflow

---

## Lab Environment

**Tools Used:**

* [Insert tool used: Splunk / Windows Event Viewer / Linux logs]
* Virtualized lab environment
* Authentication log sources

**Systems Involved:**

* [Insert source system]
* [Insert monitored system]

---

## Investigation Process

During this lab, authentication activity was collected and reviewed to identify unusual login behavior.

The investigation focused on:

* Failed authentication attempts
* Successful authentication events
* Login frequency and timing
* Potential indicators of unauthorized access

Authentication events were analyzed to determine whether activity represented normal user behavior or possible attack activity.

---

## Findings

During analysis, authentication events were reviewed for suspicious patterns including:

* Multiple failed login attempts from the same source
* Repeated authentication failures within a short timeframe
* Successful logins following multiple failed attempts
* Unusual access patterns

These behaviors can indicate password guessing, brute-force attempts, or the potential use of compromised credentials.

---

## Key Security Concepts Demonstrated

### Authentication Monitoring

Authentication logs provide visibility into who is accessing systems, when access occurs, and whether login attempts succeed or fail.

### Failed Login Analysis

A high number of failed authentication attempts may indicate:

* Brute-force attacks
* Password spraying
* Misconfigured applications
* User credential issues

### Successful Login Analysis

Successful logins should also be reviewed because attackers may use:

* Stolen credentials
* Previously compromised accounts
* Valid accounts for persistence

---

# MITRE ATT&CK Mapping

## Relevant Techniques

| Tactic            | Technique      | ID    | Description                                                                                          |
| ----------------- | -------------- | ----- | ---------------------------------------------------------------------------------------------------- |
| Credential Access | Brute Force    | T1110 | Attackers may attempt to gain access by repeatedly guessing passwords or authentication credentials. |
| Persistence       | Valid Accounts | T1078 | Attackers may use legitimate credentials to access systems and maintain access.                      |

---

## ATT&CK Analysis

This lab aligns with MITRE ATT&CK techniques related to credential-based attacks and unauthorized account access.

Monitoring authentication activity helps security teams detect behaviors associated with:

* Password guessing attempts
* Account compromise
* Unauthorized access using valid credentials

---

## Screenshots

Screenshots demonstrating the investigation process are stored in the `screenshots` directory.

Included evidence:

* Authentication log review
* Failed login activity
* Successful authentication events
* Detection analysis

---

## Lessons Learned

This lab demonstrated the importance of authentication monitoring as an early detection method for security incidents.

Key takeaways:

* Authentication logs are valuable sources of security intelligence
* Failed login patterns can reveal attack attempts
* Successful logins should be investigated when they occur after suspicious activity
* Security analysts must understand normal behavior to identify anomalies

---

## Future Improvements

Potential improvements to this lab include:

* Creating automated alerts for suspicious authentication activity
* Adding additional log sources
* Correlating authentication events with network activity
* Expanding detection coverage using SIEM rules

---

## Conclusion

Authentication monitoring is a foundational security operation skill. This lab demonstrated how analysts can use authentication data to identify suspicious behavior and investigate potential account compromise.

The techniques practiced in this lab are directly applicable to Security Operations Center (SOC) monitoring, incident response, and threat detection workflows.

