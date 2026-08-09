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
