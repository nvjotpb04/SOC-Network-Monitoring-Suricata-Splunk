# SOC Network Monitoring & Threat Detection Lab

![Splunk](https://img.shields.io/badge/SIEM-Splunk-orange)
![Suricata](https://img.shields.io/badge/IDS-Suricata-red)
![Cybersecurity](https://img.shields.io/badge/Focus-SOC%20Monitoring-blue)
![Network Security](https://img.shields.io/badge/Domain-Network%20Security-green)

## 📌 Project Overview

This project demonstrates a hands-on Security Operations Center (SOC)
network monitoring and threat detection environment using Splunk
Enterprise and Suricata IDS.

The lab focuses on centralized security monitoring, Suricata alert
analysis, network traffic visibility, dashboard development and
security event investigation.

The project was developed in an isolated laboratory environment to
practice real-world SOC monitoring and incident investigation workflows.

---

## 🎯 Objectives

- Implement network security monitoring using Suricata IDS
- Integrate Suricata security alerts with Splunk Enterprise
- Analyze network security events using SPL
- Monitor suspicious source and destination IP addresses
- Identify commonly targeted destination ports
- Analyze alert severity
- Monitor security alerts over time
- Analyze network protocols
- Monitor HTTP methods
- Build a centralized SOC monitoring dashboard
- Practice alert triage and security event investigation

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Splunk Enterprise | SIEM and security event analysis |
| Suricata IDS | Network intrusion detection |
| SPL | Security event searching and analysis |
| Linux | Suricata monitoring environment |
| Windows | Endpoint environment |
| Sysmon | Endpoint telemetry |
| VMware | Virtualized cybersecurity lab |

---

## 🏗️ Lab Architecture

The laboratory environment follows this general workflow:

```text
                    Network Traffic
                           |
                           v
                   +---------------+
                   |   Suricata    |
                   |      IDS      |
                   +-------+-------+
                           |
                    Security Alerts
                           |
                           v
                   +---------------+
                   |     Splunk    |
                   |   Enterprise  |
                   +-------+-------+
                           |
                           v
                  SOC Monitoring Dashboard
                           |
            +--------------+--------------+
            |              |              |
            v              v              v
       Alert Analysis  Network Analysis  Investigation
            |              |              |
            +--------------+--------------+
                           |
                           v
                    Analyst Findings
