# Repeated Suricata Alerts – Possible Network Scanning

## 1. Investigation Overview

This lab investigation demonstrates how a SOC analyst can identify
repeated Suricata alerts originating from the same source IP address.

Repeated alerts may indicate reconnaissance, scanning, misconfiguration,
or other unusual network activity. Additional evidence is required
before classifying the activity as malicious.

## 2. Detection Source

**Detection Source:** Suricata IDS  
**SIEM:** Splunk Enterprise  
**Event Type:** `alert`  
**Index:** `suricata`

## 3. Initial Detection

The analyst begins by identifying source IP addresses generating a high
number of security alerts.

```spl
index=suricata event_type=alert
| stats count by src_ip
| sort - count

4. Investigation Steps
Step 1 – Identify High-Volume Sources
index=suricata event_type=alert
| stats count by src_ip
| sort - count
| head 10
The result highlights source IP addresses associated with the highest
number of alerts.

Step 2 – Analyze Source and Destination
index=suricata event_type=alert
| stats count by src_ip dest_ip
| sort - count

This helps determine which destination systems are receiving traffic
from a particular source.

Step 3 – Analyze Destination Ports
index=suricata event_type=alert
| stats count by src_ip dest_port
| sort - count

Multiple destination ports associated with one source may indicate
activity that requires further investigation.

Step 4 – Review Alert Signatures
index=suricata event_type=alert
| stats count by src_ip alert.signature
| sort - count

This helps determine which Suricata signatures are repeatedly triggered
by a source.

Step 5 – Review the Timeline
index=suricata event_type=alert
| timechart count by src_ip

The analyst can use the timeline to identify sudden increases or
repeated activity.

5. Investigation Indicators
Indicator	What the Analyst Checks
Source IP	Which system generated the activity?
Alert Count	How frequently did alerts occur?
Destination IP	Which systems were targeted?
Destination Ports	Which services were contacted?
Alert Signature	What activity did Suricata detect?
Timeline	Was the activity concentrated in a short period?
6. Analyst Assessment

Repeated alerts from a single source should not automatically be
classified as malicious.

The analyst should consider:

Whether the source is an authorized system
Whether the destination is expected
Whether multiple ports were targeted
Whether the same signatures were repeatedly triggered
Whether the activity occurred within a short time period
Whether other security logs support the finding
7. Recommended Response

If the activity is determined to be suspicious, the SOC analyst may:

Continue monitoring the source IP.
Search for additional related alerts.
Correlate the activity with endpoint or firewall logs.
Escalate the incident according to SOC procedures.
Apply blocking or containment controls when authorized.
Document the investigation and evidence.
8. Investigation Outcome

Status: Lab investigation

Potential Finding: Possible network scanning or reconnaissance activity.

Confidence: Requires additional evidence.

The scenario demonstrates how a SOC analyst can move from repeated
security alerts to structured investigation and evidence-based
assessment.

9. Skills Demonstrated
Alert triage
Network security monitoring
Suricata IDS analysis
Splunk Enterprise
SPL
Source IP analysis
Destination port analysis
Timeline analysis
Event correlation
Security investigation
Incident documentation

