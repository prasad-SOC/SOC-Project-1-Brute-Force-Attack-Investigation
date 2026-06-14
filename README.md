# SOC Project 1 – Brute Force Attack Investigation

## Project Overview

This project simulates a Security Operations Center (SOC) investigation into a brute force attack against a privileged account. The objective was to analyze authentication logs, identify suspicious activity, determine the source of the attack, and document findings using a structured incident investigation process.

---

## Scenario

A security alert was generated after multiple failed login attempts were detected against a privileged account. As a SOC Analyst, I was tasked with reviewing authentication logs to determine whether malicious activity had occurred and assess the impact.

---

## Objectives

* Identify the targeted account.
* Identify the source IP address.
* Determine the number of failed login attempts.
* Verify whether a successful login occurred.
* Build an attack timeline.
* Document findings and recommendations.

---

## Tools Used

* Kali Linux
* Linux Command Line
* grep
* awk
* sort
* uniq
* wc
* GitHub

---

## Dataset

The investigation was performed using a simulated authentication log dataset containing over 5,000 authentication events.

Dataset included:

* Successful logins
* Failed logins
* Multiple user accounts
* Internal network activity
* Suspicious external authentication attempts
* Brute force attack activity

---

## Investigation Process

### Step 1: Review Authentication Logs

Authentication logs were analyzed to identify abnormal login activity and repeated authentication failures.

### Step 2: Identify Failed Login Attempts

Repeated failed login attempts were observed against the administrator account.

### Step 3: Identify Source IP

The suspicious activity originated from a single external IP address:

185.221.77.14

### Step 4: Verify Successful Authentication

Following multiple failed attempts, a successful login was observed from the same source IP address.

### Step 5: Build Timeline

A timeline of events was created to determine the sequence of the attack.

### Step 6: Document Findings

All evidence was collected and documented as part of the investigation report.

---

## Evidence Collected

| Evidence Type         | Details                       |
| --------------------- | ----------------------------- |
| Target Account        | administrator                 |
| Source IP Address     | 185.221.77.14                 |
| Failed Login Attempts | 124                           |
| Successful Login      | Yes                           |
| Attack Status         | Confirmed                     |
| Investigation Result  | Successful Brute Force Attack |

---

## Attack Timeline

| Timestamp                      | Event                                   |
| ------------------------------ | --------------------------------------- |
| 2026-06-13 02:13:01            | Initial Failed Login Attempt            |
| 2026-06-13 02:13:01 - 02:17:37 | Multiple Failed Authentication Attempts |
| During Attack Window           | Successful Login Observed               |
| Investigation Completed        | Brute Force Confirmed                   |

---

## Key Findings

### Finding 1

The administrator account was specifically targeted.

### Finding 2

A total of 124 failed authentication attempts were identified.

### Finding 3

All suspicious activity originated from a single external IP address.

### Finding 4

The attacker successfully authenticated after repeated failed attempts.

### Finding 5

The activity occurred during unusual hours (approximately 2 AM), increasing the likelihood of malicious intent.

---

## MITRE ATT&CK Mapping

| Tactic            | Technique              |
| ----------------- | ---------------------- |
| Credential Access | Brute Force (T1110)    |
| Initial Access    | Valid Accounts (T1078) |

---

## Impact Assessment

The investigation confirmed unauthorized access to a privileged account through a brute force attack.

Potential risks include:

* Unauthorized system access
* Privilege abuse
* Data exposure
* Additional attacker activity after login

---

## Recommendations

1. Enable Multi-Factor Authentication (MFA).
2. Implement account lockout policies.
3. Monitor privileged accounts for suspicious activity.
4. Block or investigate malicious IP addresses.
5. Strengthen password policies.
6. Review all activity performed after successful authentication.

---

## Lessons Learned

Through this project, I gained practical experience in:

* Authentication log analysis
* Brute force attack detection
* Incident investigation methodology
* Timeline creation
* Evidence collection and validation
* Linux-based log analysis
* Security reporting and documentation

---

## Project Outcome

This investigation successfully identified and confirmed a brute force attack against a privileged account. The findings were documented, mapped to the MITRE ATT&CK framework, and accompanied by actionable security recommendations.
