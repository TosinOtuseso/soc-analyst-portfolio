# SOC138 – Suspicious XLS File Investigation

## 📌 Overview
This project documents the investigation of a suspicious XLS file detected within a SOC environment. The goal was to determine whether the file was malicious, identify indicators of compromise (IOCs), and map attacker behavior using the MITRE ATT&CK framework.

---

# 🎯 Objectives

- Investigate suspicious XLS activity
- Analyze potential malware behavior
- Identify malicious indicators
- Map observed behavior to MITRE ATT&CK
- Recommend containment actions

---

# 🛠️ Tools Used

- SIEM Platform
- VirusTotal
- Any.Run
- MITRE ATT&CK Framework

---

# 🚨 Alert Information

| Field | Value |
|---|---|
| Alert Name | Suspicious XLS File |
| Severity | High |
| Source Host | Workstation |
| Detection Method | SIEM Alert |

---

# 🔍 Investigation Steps

## 1. Initial Alert Review

The SOC received an alert indicating that a suspicious `.xls` file was downloaded and executed on a workstation.

### Actions Taken:
- Reviewed SIEM logs
- Checked user activity
- Identified file execution events

---

## 2. File Analysis

The suspicious XLS file was analyzed using VirusTotal and sandboxing tools.

### Findings:
- Malicious macro behavior detected
- Obfuscated PowerShell execution observed
- Network connections initiated after execution

---

## 3. Network Analysis

Observed outbound traffic over HTTPS to suspicious external IP addresses.

### Indicators:
- Unknown IP communication
- Repeated outbound beaconing behavior
- Possible Command & Control (C2) activity

---

# 🧠 MITRE ATT&CK Mapping

| Tactic | Technique | ATT&CK ID |
|---|---|---|
| Initial Access | Phishing Attachment | T1566.001 |
| Execution | PowerShell | T1059.001 |
| Command & Control | Application Layer Protocol | T1071 |
| Defense Evasion | Obfuscated Files or Information | T1027 |

---

# ⚠️ Indicators of Compromise (IOCs)

| Type | Indicator |
|---|---|
| File Hash | Example SHA256 |
| IP Address | Suspicious IP |
| File Name | suspicious.xls |

---

# 🛡️ Containment Actions

- Isolated affected workstation
- Blocked malicious IP addresses
- Removed malicious file
- Conducted endpoint scan

---

# ✅ Lessons Learned

This investigation demonstrated how malicious Office documents can be used to execute obfuscated PowerShell payloads and establish outbound command-and-control communications. The case also reinforced the importance of monitoring user downloads and analyzing encrypted outbound traffic.

---


- MITRE ATT&CK
- VirusTotal
- Any.Run
