# 🔍 Security Monitoring & Incident Response Lab

## 👨‍💻 Author
Oluwaseun Quadri  

---

## 📌 Overview

This lab demonstrates hands-on experience in Security Monitoring, SIEM configuration, and Incident Response.

The objective was to simulate a brute-force SSH attack and detect, analyze, and document the incident using a SIEM solution.

The lab also includes an AI risk assessment for adversarial ML tools in cybersecurity environments.

---

## 🛠 Lab Environment

- Monitoring Platform: Security Onion / ELK Stack
- Attack Simulation Tool: Hydra
- Target Service: SSH
- Attacker Machine: Kali Linux
- Target Machine: Ubuntu Server

---

## 🎯 Objectives

- Deploy and configure SIEM solution
- Simulate SSH brute-force attack
- Detect attack via log monitoring
- Analyze attack patterns
- Map activity to MITRE ATT&CK
- Produce structured incident report
- Perform AI risk assessment

---

## 🚨 Attack Simulation

A brute-force SSH attack was simulated using Hydra against the target server.

Attack Type:
- Credential brute-force attempt

Technique:
- Multiple password attempts against SSH service

---

## 📊 Detection & Analysis

The attack was detected in the SIEM dashboard through:

- Multiple failed login attempts
- Abnormal authentication patterns
- High login attempt frequency
- Source IP identification

Logs were analyzed to determine:

- Timestamp of attack
- Attacker IP address
- Number of login attempts
- Target account

---

## 🧠 MITRE ATT&CK Mapping

Technique Identified:
- T1110 – Brute Force

Tactic:
- Credential Access

---

## 🤖 AI Risk Assessment

The lab included risk evaluation of adversarial AI tools, focusing on:

- Prompt injection risks
- Data poisoning threats
- Abuse detection
- Model misuse risks

Risk mitigation strategies were documented in the AI risk assessment report.

---

## 📁 Deliverables Included

- SIEM Dashboard Screenshots
- Hydra Attack Output
- Incident Analysis Report
- AI Tool Risk Assessment Report
- Sample Log Evidence

---

## 🔐 Skills Demonstrated

✔ SIEM Deployment & Log Analysis  
✔ Attack Detection & Investigation  
✔ Incident Documentation  
✔ MITRE ATT&CK Mapping  
✔ Risk Assessment  
✔ Defensive Security Monitoring  

---

## 🎯 Key Takeaways

This lab strengthened practical SOC-level skills in detecting and responding to active attacks, analyzing logs, and producing structured security documentation.

---
