# 🔐 Enterprise Security Monitoring & Incident Response Lab

## 👨‍💻 Author
Oluwaseun Adedamola

---

## 📌 Overview

This lab demonstrates hands-on experience in building, attacking, defending, and monitoring a small-scale enterprise security environment.

The objective was to deploy a vulnerable web application and an SSH honeypot, simulate external attacks, detect malicious activity using centralized logging, implement mitigation, and produce a structured incident response report.

Both web-layer and network-layer brute-force attacks were successfully simulated and analyzed.

---

## 🛠 Lab Environment

- Monitoring Platform: ELK Stack (Elasticsearch, Logstash, Kibana)
- Vulnerable Web Application: DVWA
- SSH Honeypot: Cowrie
- Attack Tools: Nmap, Metasploit
- Attacker Machine: Kali Linux
- Target Server: Ubuntu Server
- Defense Mechanism: UFW Firewall

---

## 🎯 Objectives

- Deploy DVWA and Cowrie honeypot
- Perform reconnaissance using Nmap
- Simulate brute-force attacks
- Detect attacks via centralized logging
- Analyze authentication patterns
- Implement firewall-based mitigation
- Produce structured incident response documentation

---

## 🚨 Attack Simulation

### 1️⃣ Reconnaissance Phase

Tool Used:
- Nmap

Activities Performed:
- Port scanning
- Service detection
- Identification of exposed services

Findings:
- Port 80 open (Web service detected)
- Port 22 open (SSH service detected)

---

### 2️⃣ Web Application Attack (DVWA)

Attack Type:
- Brute-force login attempt

Technique:
- Multiple credential attempts against DVWA login portal

Observed Indicators:
- Repeated authentication failures
- High login request frequency
- Single source IP performing multiple attempts

---

### 3️⃣ SSH Brute Force Attack (Cowrie)

Tool Used:
- Metasploit SSH login module

Attack Type:
- Credential brute-force attempt

Captured by Honeypot:
- Attacker IP address
- Attempted usernames and passwords
- Session timestamps
- Command interaction logs

---

## 📊 Detection & Analysis

The attacks were detected in the ELK dashboard through:

- Multiple failed login attempts
- Abnormal authentication patterns
- Repeated access attempts from single IP
- SSH session activity logs

Logs were analyzed to determine:

- Timestamp of attacks
- Attacker IP address
- Number of login attempts
- Targeted services (HTTP and SSH)

---

## 🧠 MITRE ATT&CK Mapping

Technique Identified:
- T1110 – Brute Force

Tactics:
- Credential Access
- Initial Access

---

## 🛑 Mitigation & Defense

Mitigation was implemented using UFW Firewall.

Action Taken:
- Inserted deny rule for attacker IP address

Result:
- Further malicious connections denied
- Successful containment of simulated threat

---

## 📁 Deliverables Included

- Network Architecture Diagram
- Nmap Scan Output
- Metasploit Attack Evidence
- ELK Dashboard Screenshots
- Firewall Rule Evidence
- Comprehensive Incident Response Report

---

## 🔐 Skills Demonstrated

✔ Network Reconnaissance  
✔ Web Application Attack Simulation  
✔ SSH Attack Simulation  
✔ SIEM Deployment & Log Analysis  
✔ Incident Detection & Investigation  
✔ Firewall Configuration  
✔ MITRE ATT&CK Mapping  
✔ Defensive Security Monitoring  

---

## 🎯 Key Takeaways

This lab strengthened practical SOC-level skills in detecting, analyzing, and responding to web and SSH brute-force attacks within a simulated enterprise environment.
