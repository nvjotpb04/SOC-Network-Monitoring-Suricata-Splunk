# 🛡️ SOC Network Monitoring & Threat Detection Lab

![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Suricata](https://img.shields.io/badge/IDS-Suricata-red)
![SOC](https://img.shields.io/badge/Focus-SOC%20Monitoring-blue)
![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-green)

## 📌 Project Overview

A hands-on Security Operations Center (SOC) network monitoring and threat
detection lab built using **Splunk Enterprise** and **Suricata IDS**.

The project demonstrates how security alerts can be collected, analyzed
and visualized through a centralized SIEM platform. It focuses on network
security monitoring, alert triage, threat detection and investigation.

The environment was developed in an isolated laboratory for educational
and defensive cybersecurity purposes.

---

## 🎯 Objectives

- Build a practical SOC monitoring environment
- Integrate Suricata IDS with Splunk Enterprise
- Monitor network security alerts
- Analyze security events using SPL
- Identify suspicious source IP addresses
- Identify targeted destination systems
- Monitor destination ports
- Analyze alert severity
- Detect unusual alert spikes
- Analyze network protocols
- Monitor HTTP methods
- Develop a centralized SOC dashboard
- Practice security alert triage and investigation

---

## 🛠️ Technologies & Tools

| Technology | Role |
|---|---|
| **Splunk Enterprise** | SIEM, log analysis and visualization |
| **Suricata IDS** | Network intrusion detection |
| **SPL** | Security event searching and analysis |
| **Linux** | Security monitoring environment |
| **Windows** | Endpoint environment |
| **Sysmon** | Windows endpoint telemetry |
| **VMware** | Virtualized laboratory environment |

---

# 🏗️ Architecture

The lab follows a centralized security monitoring workflow:

```text
                    Network Traffic
                           │
                           ▼
                  ┌─────────────────┐
                  │    Suricata     │
                  │       IDS       │
                  └────────┬────────┘
                           │
                     Security Alerts
                           │
                           ▼
                  ┌─────────────────┐
                  │     Splunk      │
                  │   Enterprise    │
                  └────────┬────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │  SOC Dashboard    │
                 └─────────┬─────────┘
                           │
              ┌────────────┼────────────┐
              ▼            ▼            ▼
         Alert Triage  Investigation  Analysis
              │            │            │
              └────────────┼────────────┘
                           ▼
                    Analyst Findings
