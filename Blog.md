# SOC Project 1: Investigating a Brute Force Attack Using Authentication Logs

## Introduction

In this project, I stepped into the role of a SOC Analyst and investigated a suspected brute force attack using authentication logs. The goal was to identify suspicious activity, determine whether an account was compromised, and document the findings like a real security incident investigation.

To make the investigation more realistic, I worked with a dataset containing more than 5,000 authentication events, including normal user activity and hidden malicious behavior.

---

## Scenario

A security alert was triggered due to an unusually high number of failed login attempts against a privileged account.

My task was to investigate the authentication logs and answer the following questions:

* Which account was targeted?
* Where did the activity originate from?
* How many failed login attempts occurred?
* Was the attack successful?
* What evidence supports the conclusion?

---

## Setting Up the Investigation

I imported the authentication log dataset into my Kali Linux environment and began reviewing the logs using common Linux commands.

The dataset contained:

* Successful login events
* Failed login events
* Multiple user accounts
* Internal network activity
* External authentication attempts
* Suspicious login behavior

Since the dataset contained over 5,000 events, the challenge was to identify the malicious activity hidden among legitimate user activity.

---

## Reviewing the Logs

The first step was to understand the overall authentication activity.

I used Linux commands to:

* Count total log entries
* Identify failed login attempts
* Identify successful logins
* Search for suspicious accounts
* Identify source IP addresses
* Build a timeline of events

As I reviewed the logs, one account immediately stood out.

---

## Discovering the Target Account

The account receiving repeated login attempts was:

```text
administrator
```

This was a major indicator because attackers often target privileged accounts in an attempt to gain elevated access.

---

## Identifying the Source IP

Next, I reviewed the source IP addresses associated with the suspicious authentication activity.

The repeated login attempts originated from:

```text
185.221.77.14
```

The activity from this IP address was significantly different from normal user behavior.

---

## Counting Failed Login Attempts

After filtering the authentication events, I discovered:

```text
124 Failed Login Attempts
```

These attempts were directed at the administrator account within a short time period.

A high volume of repeated failures against a single account is a classic indicator of a brute force attack.

---

## Building the Timeline

The attack occurred between:

```text
2026-06-13 02:13:01
```

and

```text
2026-06-13 02:17:37
```

This timing was suspicious because it occurred during early morning hours when legitimate user activity is typically low.

The sequence of events followed a clear pattern:

1. Multiple failed login attempts
2. Continued password guessing
3. Successful authentication

---

## Confirming the Attack

After reviewing the logs, I confirmed that the attack was successful.

The same source IP responsible for the failed attempts eventually achieved a successful login to the administrator account.

This transformed the incident from a simple attack attempt into a confirmed account compromise.

The evidence showed:

* 124 failed login attempts
* Single source IP address
* Targeting of a privileged account
* Successful authentication after repeated failures
* Unusual attack timing

Together, these indicators confirmed a brute force attack.

---

## Impact Assessment

Because the attacker successfully authenticated to a privileged account, the incident should be considered high severity.

Potential risks include:

* Unauthorized system access
* Privilege abuse
* Data exposure
* Further attacker activity inside the environment

In a real-world environment, this would require immediate containment and additional investigation.

---

## Recommendations

Based on the findings, I would recommend:

1. Reset the compromised account password.
2. Enable Multi-Factor Authentication (MFA).
3. Implement account lockout policies.
4. Monitor privileged accounts more closely.
5. Block or investigate the malicious IP address.
6. Strengthen password requirements.

---

## MITRE ATT&CK Mapping

This activity aligns with the following techniques:

| Tactic            | Technique              |
| ----------------- | ---------------------- |
| Credential Access | Brute Force (T1110)    |
| Initial Access    | Valid Accounts (T1078) |

---

## What I Learned

This project helped me practice:

* Authentication log analysis
* Linux-based investigations
* Brute force attack detection
* Timeline creation
* Evidence collection
* Incident reporting
* SOC investigation methodology

One of the biggest lessons from this project was understanding how malicious activity can be hidden within thousands of legitimate log entries. By following a structured investigation process, I was able to identify the attacker, confirm the compromise, and document the incident.

---

## Conclusion

In this project, I investigated a brute force attack using over 5,000 authentication log events. Through log analysis, I identified the targeted account, traced the source IP address, confirmed 124 failed login attempts, and verified a successful compromise of the administrator account.

This project provided practical experience in security monitoring, incident investigation, and evidence-based decision-making, all of which are essential skills for a SOC Analyst.
