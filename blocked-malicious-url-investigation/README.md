# Malicious URL Blocked by Firewall Investigation

## Overview

This investigation was performed in a SOC simulation environment using Splunk SIEM.

The alert was triggered after an attempt to access a malicious URL identified by the organization's security controls.

The objective of the investigation was to determine the source of the access attempt, validate the Indicators of Compromise (IOCs), and verify whether any endpoint compromise occurred.

---

## Alert Information

| Field | Value |
|--------|--------|
| Alert ID | 8816 |
| Severity | High |
| Incident Type | Firewall |
| Action | Blocked |
| Source IP | 10.20.2.17 |
| Destination IP | 67.199.248.11 |

---

## Timeline

| Time | Event |
|------|------|
| 18:46:00 | User received a phishing email |
| 18:47:14 | Firewall blocked access to a malicious URL |

---

## Indicators of Compromise (IOCs)

### URL

```text
http://bit.ly/3sHkX3da12340
```

### IP Address

```text
67.199.248.11
```

### Sender

```text
urgents@amazon.biz
```

### Recipient

```text
h.harris@thetrydaily.thm
```

---

## Evidence

During the investigation, the following findings were identified:

- The user received a phishing email impersonating Amazon Delivery.
- The email contained a shortened URL using the bit.ly service.
- The URL was associated with IP address 67.199.248.11.
- URL/IP analysis identified the destination as malicious.
- Firewall logs confirmed that the connection attempt was blocked.
- No evidence of malware execution or endpoint compromise was identified.

---

## Conclusion

The incident was classified as a True Positive.

A confirmed attempt was made to access a malicious URL delivered through a phishing email. The firewall successfully blocked the connection, preventing potential malicious activity.

No signs of endpoint compromise were identified during the investigation.

---

## Recommended Actions

- Maintain the IOC blocked across all security controls.
- Continue monitoring the affected endpoint for suspicious activity.
- Verify whether other users received the same phishing email.
- Reinforce phishing awareness training for employees.
- Review email filtering policies to reduce future phishing attempts.

## IP Adress 
- 67.199.248.11

## Sender
- urgents@amazon.biz
