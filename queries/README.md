# Kusto Query Language (KQL) Library

This directory contains the Kusto Query Language (KQL) queries developed during the Microsoft Sentinel SOC Engineering Handbook project.

The queries demonstrate the complete security operations workflow, from validating data ingestion to threat hunting, detection engineering, incident investigation, and production-ready Microsoft Sentinel Analytics Rules.

---

## Directory Structure

| Folder | Purpose |
|----------|---------|
| **parsing/** | Validate data ingestion, inspect raw logs, and extract fields from custom log sources. |
| **hunting/** | Ad-hoc queries used to proactively identify suspicious activity and potential threats. |
| **detection/** | Detection engineering queries that identify malicious behavior based on predefined logic. |
| **investigation/** | Queries used during incident triage and forensic investigation. |
| **analytics-rules/** | Optimized KQL queries intended for Microsoft Sentinel Scheduled Analytics Rules. |

---

## Skills Demonstrated

- Kusto Query Language (KQL)
- Log Parsing
- Threat Hunting
- Detection Engineering
- Incident Investigation
- Microsoft Sentinel
- Azure Log Analytics
- MITRE ATT&CK Mapping
- Security Analytics

---

## Data Source

The queries in this repository were developed using a custom Log Analytics table:

```
MeridianLogs_CL
```

The dataset contains Linux SSH authentication events used to simulate SOC monitoring and incident response workflows.

---

## Query Categories

### Parsing

Focuses on validating telemetry and preparing data for analysis.

Examples:

- Validate data ingestion
- Preview raw events
- Count ingested events
- Extract source IP addresses

---

### Threat Hunting

Supports proactive security investigations.

Examples:

- Failed SSH logins
- Top attacking IPs
- Authentication summaries
- Suspicious IP analysis

---

### Detection Engineering

Transforms hunting logic into repeatable detections.

Examples:

- Brute-force detection
- Failed login thresholds
- High-risk source IP detection

---

### Investigation

Supports analyst triage and incident response.

Examples:

- Timeline analysis
- Host investigation
- Incident investigation

---

### Analytics Rules

Production-ready queries optimized for Microsoft Sentinel Scheduled Analytics Rules.

These queries are designed for alert generation and include threshold tuning and entity mapping considerations.

---

## Notes

These queries are intended for educational purposes and demonstrate security operations workflows using Microsoft Sentinel and Azure Log Analytics. They may require modification before deployment in production environments.
