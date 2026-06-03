# Blocked Malicious URL Investigation

## Overview

This investigation was conducted in a SOC simulation environment using Splunk SIEM.

The alert was triggered after an attempt to access a malicious URL identified by the organization's security controls.

The objective of the investigation was to determine the source of the access attempt, validate the involved Indicators of Compromise (IOCs), and verify whether any host compromise occurred.

---

## Alert Information

| Field | Value |
|---|---|
| Alert ID | 8816 |
| Severity | High |
| Incident Type | Firewall |
| Action | Blocked |
| Source IP | 10.20.2.17 |
| Destination IP | 67.199.248.11 |

---

## Indicators of Compromise (IOCs)

### Malicious URL

```text
http://bit.ly/3sHkX3da12340
```

### Email Sender

```text
urgents@amazon.biz
```

### Email Subject

```text
Your Amazon Package Couldn't Be Delivered - Action Required
```

### Destination IP

```text
67.199.248.11
```

---

## Investigation Process

### 1. Initial Analysis

A firewall alert was identified indicating an attempt to access a URL present in the organization's blocklist.

### 2. Log Correlation

Splunk searches were performed to identify:

- The origin of the URL
- Source host activity
- Related events involving the destination IP
- The source of the access attempt

### 3. Findings

A phishing email sent from:

```text
urgents@amazon.biz
```

was identified containing the URL:

```text
http://bit.ly/3sHkX3da12340
```

The investigation confirmed that the user attempted to access the URL contained in the phishing email.

The firewall successfully detected the URL as malicious and blocked the connection using the following rule:

```text
Blocked Websites
```

An earlier legitimate Google search was also identified and determined to be unrelated to the malicious activity.

---

## Conclusion

The incident was classified as a True Positive.

The investigation confirmed an attempt to access a malicious URL distributed through a phishing email.

The firewall successfully blocked the connection, and no evidence of host compromise or malware execution was identified during the investigation.

---

## Recommendations

- Maintain the IOC blocked within security controls.
- Continue monitoring the affected host for suspicious activity.
- Review phishing protection policies.
- Provide phishing awareness training to users.
- Consider a precautionary password reset if additional suspicious activity is identified.

---

## Skills Demonstrated

- Firewall Investigation
- IOC Analysis
- Log Correlation
- Splunk SIEM
- Phishing Analysis
- Incident Triage
- Threat Validation
