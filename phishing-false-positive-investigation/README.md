# Phishing False Positive Investigation

## Overview
This investigation was performed in a SOC simulation environment using Splunk SIEM.

An alert was triggered due to an external onboarding email containing a suspicious URL.

The objective of the investigation was to determine whether the recipient interacted with the embedded link and whether any malicious activity occurred.

---

## Alert Information

| Field | Value |
|---|---|
| Alert ID | 8814 |
| Severity | Medium |
| Incident Type | Phishing |
| Recipient | j.garcia@thetrydaily.thm |
| Sender | onboarding@hrconnex.thm |

---

## Suspicious URL

```text
https://hrconnex.thm/onboarding/15400654060/j.garcia
```

---

## Investigation Process

### 1. Initial Email Analysis
- Reviewed the phishing alert
- Identified external onboarding URL
- Confirmed no attachment was present

### 2. SIEM Investigation
Performed searches within Splunk SIEM to identify related activity.

#### Search Queries Used

```spl
j.garcia AND hrconnex
```

```spl
hrconnex NOT datasource=email
```

### 3. Findings
- Only email-related logs were identified
- No proxy, firewall, DNS, or web access logs were found
- No evidence indicated that the user accessed the embedded URL
- Domain activity appeared consistent with a legitimate onboarding process

---

## Related Entities

- j.garcia@thetrydaily.thm
- onboarding@hrconnex.thm
- hrconnex.thm
- https://hrconnex.thm/onboarding/15400654060/j.garcia

---

## Conclusion

The alert was classified as a false positive because no evidence of malicious activity or user interaction with the embedded URL was identified.

The investigation determined that the activity was most likely related to a legitimate onboarding workflow.

---

## Skills Demonstrated

- SIEM Investigation
- Splunk Log Analysis
- Phishing Triage
- Log Correlation
- False Positive Validation
- SOC Documentation
