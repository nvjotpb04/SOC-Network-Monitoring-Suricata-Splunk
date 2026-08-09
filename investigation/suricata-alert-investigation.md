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
