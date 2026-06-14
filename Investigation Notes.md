# Investigation Notes – Brute Force Attack Investigation

## Analyst Information

**Project:** SOC Project 1 – Brute Force Attack Investigation

**Investigation Type:** Authentication Log Analysis

**Platform:** Kali Linux

**Dataset:** authentication_logs.txt

---

## Alert Summary

A security alert was generated due to an unusually high number of failed login attempts against a privileged account.

The objective of this investigation was to determine:

* Whether malicious activity occurred
* Which account was targeted
* The source of the activity
* Whether access was successfully obtained
* The overall impact of the incident

---

## Initial Observations

While reviewing authentication logs, a large number of failed login attempts were identified against a single account within a short period of time.

The activity occurred during early morning hours, which is unusual compared to normal user authentication patterns.

---

## Evidence Collected

### Targeted Account

```text
administrator
```

The administrator account was repeatedly targeted throughout the attack.

---

### Source IP Address

```text
185.221.77.14
```

All suspicious authentication attempts originated from this external IP address.

---

### Failed Login Attempts

```text
124
```

A total of 124 failed authentication attempts were identified.

The repeated failures indicate an automated password-guessing attack.

---

### Successful Authentication

```text
Yes
```

Following the failed login attempts, a successful login was recorded from the same source IP address.

This confirms that the attacker eventually obtained valid credentials.

---

## Attack Timeline

### Attack Start

```text
2026-06-13 02:13:01
```

First failed login attempt observed.

---

### Attack Activity

Between 02:13:01 and 02:17:37, repeated authentication attempts were made against the administrator account.

---

### Successful Access

A successful login was observed from the same source IP after multiple failed attempts.

---

### Attack End

```text
2026-06-13 02:17:37
```

Final suspicious activity recorded during the investigation window.

---

## Indicators of Compromise (IOCs)

### Suspicious IP Address

```text
185.221.77.14
```

### Targeted User Account

```text
administrator
```

### Attack Pattern

```text
Repeated failed logins followed by successful authentication
```

### Unusual Login Time

```text
Approximately 02:00 AM
```

---

## Analysis

The authentication logs revealed a clear brute force pattern.

Key indicators included:

* High volume of failed login attempts
* Single source IP address
* Targeting of a privileged account
* Activity occurring during unusual hours
* Successful login after repeated failures

These indicators strongly suggest credential guessing activity.

---

## Findings

### Finding 1

The administrator account was specifically targeted.

### Finding 2

The attack originated from a single external IP address.

### Finding 3

124 failed login attempts were recorded.

### Finding 4

The attacker successfully authenticated.

### Finding 5

The activity occurred during low-user activity hours.

### Finding 6

The attack was consistent with brute force behavior.

---

## Investigation Conclusion

The investigation confirmed a successful brute force attack against the administrator account.

The attacker performed 124 failed authentication attempts from IP address 185.221.77.14 before successfully authenticating.

Based on the evidence collected, the incident should be classified as a confirmed security event requiring immediate remediation and review of all post-compromise activity.

---

## Recommended Actions

* Reset administrator account credentials.
* Enable Multi-Factor Authentication (MFA).
* Implement account lockout policies.
* Monitor privileged account activity.
* Block or investigate the source IP address.
* Review activity performed after successful authentication.
* Strengthen password security requirements.
