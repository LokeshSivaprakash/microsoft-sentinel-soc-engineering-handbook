<div align="center">

# Microsoft Sentinel SOC Engineering Handbook

### Building a Cloud-Native Security Operations Center (SOC) with Microsoft Sentinel

**Azure Monitor • Azure Log Analytics • Microsoft Sentinel • KQL • Detection Engineering • Threat Hunting • Incident Response • MITRE ATT&CK**

![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Microsoft Sentinel](https://img.shields.io/badge/Microsoft%20Sentinel-5E5E5E?style=for-the-badge)
![KQL](https://img.shields.io/badge/KQL-00599C?style=for-the-badge)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red?style=for-the-badge)
![Blue Team](https://img.shields.io/badge/Blue-Team-blue?style=for-the-badge)
![SIEM](https://img.shields.io/badge/SIEM-Security-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

</div>

---

# Executive Summary

Modern Security Operations Centers generate and analyze millions of security events every day. Transforming raw telemetry into actionable security intelligence requires more than log collection—it requires effective detection engineering, threat hunting, incident investigation, and response.

This repository documents the design and implementation of a cloud-native SOC using **Microsoft Sentinel** and **Azure Log Analytics**. It covers the complete lifecycle of a security event:

- Data Collection
- Log Ingestion
- Data Normalization
- Threat Hunting
- Detection Engineering
- Analytics Rules
- Incident Investigation
- MITRE ATT&CK Mapping
- Incident Response

This project is designed as both a **learning resource** and a **technical portfolio** demonstrating practical Microsoft Sentinel engineering skills.

---

# Project Goals

The primary objective of this project is to understand how Microsoft Sentinel can be used to detect, investigate, and respond to cybersecurity threats.

The project focuses on:

- Building a Microsoft Sentinel environment
- Understanding Azure Log Analytics
- Writing efficient KQL queries
- Developing detection rules
- Performing threat hunting
- Investigating authentication logs
- Mapping attacker techniques to MITRE ATT&CK
- Applying incident response methodology
- Documenting engineering decisions

---

# Skills Demonstrated

| Domain | Skills |
|---------|---------|
| Cloud Security | Azure Monitor, Azure Log Analytics, Microsoft Sentinel |
| SIEM | Data Collection, Log Analysis, Alerting |
| Detection Engineering | KQL, Analytics Rules |
| Threat Hunting | Authentication Analysis, IOC Investigation |
| Incident Response | Triage, Investigation, Containment |
| Frameworks | MITRE ATT&CK |
| Security Operations | SOC Workflow |

---

# Technologies Used

| Technology | Purpose |
|------------|----------|
| Microsoft Sentinel | Cloud-native SIEM |
| Azure Log Analytics | Log Storage & Query Engine |
| Azure Monitor | Log Collection |
| Kusto Query Language (KQL) | Threat Detection |
| Azure Data Collector API | Custom Log Ingestion |
| MITRE ATT&CK | Threat Classification |

---

# SOC Architecture

```
                    Security Logs

Linux      Windows      Azure      Microsoft 365
   │           │            │              │
   └───────────┴────────────┴──────────────┘
                        │
                        ▼
                Azure Monitor
                        │
                        ▼
         Azure Log Analytics Workspace
                        │
                        ▼
             Microsoft Sentinel SIEM
                        │
        ┌───────────────┼────────────────┐
        │               │                │
        ▼               ▼                ▼
 Analytics Rules   Threat Hunting    Incidents
        │
        ▼
 SOC Analyst Investigation
        │
        ▼
 Incident Response
```

---

# Repository Structure

```
microsoft-sentinel-soc-engineering-handbook/

README.md

docs/

queries/

diagrams/

screenshots/

reports/

assets/
```

---

# Documentation Roadmap

| Section | Description |
|----------|-------------|
| 01 - Introduction | Project Overview |
| 02 - SOC Fundamentals | SIEM Concepts |
| 03 - Azure Monitor | Log Collection |
| 04 - Log Analytics | Data Storage |
| 05 - Microsoft Sentinel | SIEM Deployment |
| 06 - Log Ingestion | Data Collector API |
| 07 - KQL Fundamentals | Query Language |
| 08 - Threat Hunting | Hunting Methodology |
| 09 - Detection Engineering | Detection Development |
| 10 - Analytics Rules | Alert Generation |
| 11 - Incident Investigation | Investigation Workflow |
| 12 - Incident Response | Containment |
| 13 - MITRE ATT&CK | Threat Mapping |
| 14 - Production Improvements | Enterprise Enhancements |
| 15 - Interview Guide | Technical Interview Preparation |

---

# Detection Engineering Workflow

```
Raw Logs

↓

Normalization

↓

KQL Parsing

↓

Detection Logic

↓

Analytics Rule

↓

Incident

↓

SOC Investigation

↓

Response

↓

Lessons Learned
```

---

# Threat Scenario

This project investigates an SSH brute-force attack.

Detection methodology:

- Parse authentication logs
- Extract source IP addresses
- Count failed authentication attempts
- Detect excessive login failures
- Investigate suspicious IPs
- Classify incidents
- Recommend containment actions

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|----|
| Brute Force | T1110 |
| Valid Accounts | T1078 |

---

# Example Detection Query

```kusto
MeridianLogs_CL
| where RawData has "Failed password"
| extend SourceIP = extract(@"from ([0-9.]+)",1,RawData)
| where isnotempty(SourceIP)
| summarize Attempts=count() by SourceIP
| where Attempts > 5
```

---

# Learning Outcomes

By completing this project, you will understand:

- Cloud-native SIEM architecture
- Azure Log Analytics
- Microsoft Sentinel deployment
- KQL fundamentals
- Threat hunting
- Detection engineering
- Incident investigation
- MITRE ATT&CK mapping
- Security Operations Center workflows

---

# Future Enhancements

Planned improvements include:

- GeoIP enrichment
- Threat Intelligence integration
- Watchlists
- Automation using Logic Apps
- SOAR playbooks
- User and Entity Behavior Analytics (UEBA)
- Microsoft Defender integration
- Microsoft Entra ID log correlation
- Multi-stage attack correlation
- Custom workbooks and dashboards

---

# Screenshots

Screenshots will be added throughout the documentation to illustrate:

- Azure Resource Group
- Azure Log Analytics Workspace
- Microsoft Sentinel
- Data Connectors
- KQL Queries
- Analytics Rules
- Incidents
- Investigation Timeline

---

# References

- Microsoft Sentinel Documentation
- Azure Monitor Documentation
- Azure Log Analytics Documentation
- Microsoft Learn
- MITRE ATT&CK Framework

---

# About This Repository

This repository was developed as a practical cybersecurity engineering project to demonstrate hands-on experience with Microsoft Sentinel, Azure Log Analytics, detection engineering, and incident response. It is intended as a technical reference for students, security professionals, and hiring managers interested in evaluating practical SIEM engineering skills.

---

# Author

**Lokesh Sivaprakash**

Master of Information Systems  
Cloud Security | Detection Engineering | SOC | Microsoft Sentinel | Azure | KQL

---

## License

This project is licensed under the MIT License.
