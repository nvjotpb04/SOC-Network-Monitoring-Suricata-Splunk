# Suricata Alert Investigation – Suspicious Network Activity

## 1. Investigation Overview

This investigation demonstrates a SOC analyst workflow for analyzing a
Suricata IDS alert using Splunk Enterprise.

The scenario is performed in an isolated security laboratory and is
intended for defensive cybersecurity training.

## 2. Alert Source

**Detection Source:** Suricata IDS  
**SIEM:** Splunk Enterprise  
**Event Type:** `alert`  
**Data Index:** `suricata`

Example search:

```spl
index=suricata event_type=alert

3. Investigation Workflow

The investigation follows these steps:

Identify the Suricata alert.
Review the alert signature.
Identify the source IP address.
Identify the destination IP address.
Review the destination port.
Identify the network protocol.
Check the alert severity.
Review the event timestamp.
Search for repeated activity from the same source.
Determine whether the activity requires further investigation.
4. Key Indicators to Review
Indicator	Investigation Question
Alert Signature	What type of activity was detected?
Source IP	Which system generated the traffic?
Destination IP	Which system was targeted?
Destination Port	Which service was targeted?
Protocol	Which network protocol was involved?
Severity	How serious is the alert?
Timestamp	When did the activity occur?
Alert Frequency	Was the activity repeated?
5. Alert Frequency Analysis

To identify repeated activity from a source IP:

index=suricata event_type=alert
| stats count by src_ip
| sort - count

A high number of alerts from the same source may require additional
investigation.

6. Source and Destination Analysis

Analyze communication between source and destination systems:

index=suricata event_type=alert
| stats count by src_ip dest_ip
| sort - count

This helps identify frequently observed communication pairs.

7. Port Analysis

Review destination ports associated with alerts:

index=suricata event_type=alert
| stats count by dest_port
| sort - count

The analyst can investigate whether the targeted port corresponds to an
expected service.

8. Severity Analysis

Review the severity distribution:

index=suricata event_type=alert
| stats count by alert.severity
| sort - count

Higher-severity events should generally receive greater investigation
priority.

9. Analyst Assessment

The analyst should not determine that an event is malicious based only
on a single Suricata alert.

Additional context should be reviewed, including:

Source reputation
Destination system
Targeted service
Alert frequency
Related network events
Event timeline
Other security telemetry
10. Recommended Response

Depending on the investigation findings, a SOC analyst may:

Continue monitoring the source.
Search for related alerts.
Correlate activity with other security logs.
Escalate high-confidence suspicious activity.
Document the investigation.
Block or contain the source when authorized by the organization's
incident response process.
11. Investigation Outcome

Status: Lab investigation

Conclusion:
The investigation demonstrates the process of triaging and analyzing
Suricata network security alerts using Splunk Enterprise.

No conclusion of malicious activity should be made without sufficient
supporting evidence.

12. Skills Demonstrated
SOC alert triage
Suricata IDS analysis
Splunk investigation
SPL
Network traffic analysis
IP analysis
Port analysis
Security event correlation
Incident documentation
