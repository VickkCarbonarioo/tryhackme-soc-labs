# Microsoft Phishing Link Investigation

## Overview

This investigation was conducted in a SOC simulation environment using Splunk SIEM.

An alert was generated after a user received a phishing email impersonating Microsoft Account Security. The email contained a malicious URL designed to trick the recipient into visiting a fraudulent login page.

The objective of the investigation was to determine whether the user interacted with the phishing link and assess the potential security impact.

---

## Alert Information

| Field | Value |
|---------|---------|
| Alert ID | 8817 |
| Severity | Medium |
| Incident Type | Phishing |
| Recipient | c.allen@thetrydaily.thm |
| Sender | no-reply@m1crosoftsupport.co |

---

## Investigation Timeline

| Time | Event |
|--------|--------|
| 18:48:18 | Phishing email received |
| 18:49:27 | User accessed malicious URL |
| 18:49:27 | Firewall allowed outbound connection |

---

## Indicators of Compromise (IOCs)

### Malicious Sender

```text
no-reply@m1crosoftsupport.co

### Malicious Domain
m1crosoftsupport.co

### Malicious URL
https://m1crosoftsupport.co/login

### Destination IP
45.148.10.131

### IP Referenced in Email
102.89.222.143

### Investigation Findings
The email attempted to impersonate Microsoft Account Security by claiming an unusual sign-in event from Nigeria.

The sender domain used a typosquatting technique by replacing the letter "i" with the number "1" in the word Microsoft.

Firewall logs confirmed that the user accessed the phishing URL shortly after receiving the email.

The connection was allowed by the firewall, increasing the risk of credential theft or additional malicious activity.

No evidence of malware execution was identified during the investigation.

### Incident Classification
True Positive

The malicious URL was verified and the user successfully accessed the phishing website.

### Recommended Actions
Block the malicious domain.
Block the malicious URL.
Reset the user's password.
Review authentication logs.
Monitor the affected endpoint.
Perform an endpoint security scan.

### Skills Demonstrated
Phishing Investigation
IOC Analysis
Firewall Log Analysis
Splunk SIEM Investigation
Threat Correlation
Incident Documentation
