# Evidence Report – Brute Force Attack Investigation

## Evidence Summary

This document contains the evidence collected during the investigation of a brute force attack targeting a privileged account.

---

# Evidence 1 – Authentication Log Dataset

**Source File**

```text
authentication_logs.txt
```

**Description**

The authentication log dataset contained more than 5,000 authentication events including:

* Successful logins
* Failed logins
* Internal user activity
* External authentication attempts
* Suspicious login behavior

This dataset served as the primary source of evidence during the investigation.

---

# Evidence 2 – Targeted Account

**Account Name**

```text
administrator
```

**Observation**

The administrator account received a high volume of authentication attempts within a short period of time.

The repeated targeting of a privileged account is a strong indicator of malicious intent.

---

# Evidence 3 – Source IP Address

**Source IP**

```text
185.221.77.14
```

**Observation**

All suspicious authentication activity originated from the same external IP address.

This IP was responsible for the repeated failed login attempts and the eventual successful authentication.

---

# Evidence 4 – Failed Authentication Attempts

**Count**

```text
124 Failed Login Attempts
```

**Observation**

The logs showed a sequence of failed authentication attempts against the administrator account.

The number of failed attempts exceeded normal user behavior and demonstrated a clear brute force pattern.

---

# Evidence 5 – Successful Authentication

**Result**

```text
Successful Login Confirmed
```

**Observation**

After 124 failed attempts, a successful authentication event was recorded from the same source IP address.

This indicates that valid credentials were eventually obtained or guessed.

---

# Evidence 6 – Attack Timeline

| Time                 | Event                              |
| -------------------- | ---------------------------------- |
| 02:13:01             | First Failed Login Attempt         |
| 02:13 - 02:17        | Repeated Failed Logins             |
| During Attack Window | Successful Authentication          |
| 02:17:37             | Final Suspicious Activity Observed |

**Observation**

The attack occurred within a short time period and followed a repetitive authentication pattern.

---

# Evidence 7 – Unusual Login Time

**Time Window**

```text
02:13:01 – 02:17:37
```

**Observation**

The attack occurred during early morning hours when legitimate user activity is generally low.

This timing increases the likelihood that the activity was malicious.

---

# Evidence 8 – Brute Force Pattern

**Observed Behavior**

```text
Repeated Failed Logins
          ↓
Repeated Failed Logins
          ↓
Repeated Failed Logins
          ↓
Successful Login
```

**Observation**

The attack followed the classic brute force sequence where an attacker repeatedly attempts authentication until valid credentials are obtained.

---

# Evidence Analysis

The collected evidence demonstrates:

* Targeting of a privileged account
* High-volume authentication failures
* Single external source IP
* Successful authentication after repeated failures
* Unusual attack timing

Together, these indicators provide sufficient evidence to classify the incident as a confirmed brute force attack.

---

# Final Evidence Assessment

| Evidence Item                | Status                       |
| ---------------------------- | ---------------------------- |
| Target Account Identified    | Confirmed                    |
| Source IP Identified         | Confirmed                    |
| Failed Attempts Counted      | Confirmed                    |
| Successful Login Verified    | Confirmed                    |
| Timeline Established         | Confirmed                    |
| Brute Force Pattern Observed | Confirmed                    |
| Incident Classification      | Confirmed Brute Force Attack |

---

## Evidence Conclusion

The collected evidence confirms that the administrator account was targeted by a brute force attack originating from IP address 185.221.77.14. The attacker conducted 124 failed authentication attempts before successfully accessing the account. The activity occurred during unusual hours and exhibited behavior consistent with credential-guessing attacks.
