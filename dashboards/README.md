# SOC Monitoring Dashboard

## Overview

The SOC monitoring dashboard was developed in Splunk Enterprise to provide
centralized visibility into Suricata network security alerts.

The dashboard helps a SOC analyst perform initial alert triage and identify
potentially suspicious network activity.

## Dashboard

![SOC Dashboard](soc-dashboard.png)

## Monitoring Panels

| Panel | Purpose |
|---|---|
| Suricata Alert Signatures | Monitor detected security signatures |
| Destination Ports | Identify commonly targeted ports |
| Source IP Addresses | Identify high-volume alert sources |
| Destination IP Addresses | Identify targeted systems |
| Alert Severity Distribution | Prioritize alerts by severity |
| Alerts Over Time | Identify unusual alert spikes |
| Network Protocols | Analyze network communication |
| HTTP Methods | Monitor web traffic behavior |

## SOC Analyst Workflow

```text
Alert
  ↓
Initial Triage
  ↓
Identify Source
  ↓
Identify Destination
  ↓
Review Port
  ↓
Review Signature
  ↓
Check Severity
  ↓
Analyze Timeline
  ↓
Correlate Events
  ↓
Document Findings
