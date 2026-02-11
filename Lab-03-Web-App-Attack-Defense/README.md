# Web Application Attack and Defense Lab (Lab 3)

## 📌 Overview
This lab demonstrates a full attack and defense cycle on a vulnerable web application (PrestaShop). 

The objective was to:
- Identify vulnerabilities using OWASP ZAP
- Map findings to OWASP Top 10
- Deploy a Web Application Firewall (ModSecurity)
- Validate security improvements

---

## 🛠 Environment Setup

### Target Application
- PrestaShop (E-commerce platform)
- Ubuntu Server
- Apache 2.4

### Attacker Machine
- Kali Linux
- OWASP ZAP

---

## 🔍 Phase 1: Attack (Vulnerability Assessment)

Using OWASP ZAP Active Scan, the following vulnerabilities were identified:

- Cross-Site Scripting (XSS)
- Missing Anti-CSRF Tokens
- Cookie security misconfiguration
- Information disclosure via headers

These findings align with OWASP Top 10 categories.

Screenshots available in `/screenshots` directory.

---

## 🛡 Phase 2: Defense (WAF Deployment)

ModSecurity was installed and configured with:

```
SecRuleEngine On
```

OWASP Core Rule Set (CRS) was enabled to block common attack patterns.

Configuration file available in `/config`.

---

## ✅ Phase 3: Validation

After enabling the WAF:

- Multiple attack attempts were blocked
- HTTP 403 responses observed
- Reduced alerts in OWASP ZAP
- ModSecurity audit logs confirmed mitigation

This demonstrates effective implementation of layered security.

---

## 📁 Repository Structure

- `/report` → Full lab report (PDF)
- `/screenshots` → Evidence of attack and defense
- `/config` → WAF configuration file

---

## 🎯 Key Learning Outcomes

- Practical use of OWASP ZAP
- Understanding OWASP Top 10 vulnerabilities
- Real-world deployment of ModSecurity WAF
- Attack vs Defense validation workflow

---

## 📚 Tools Used

- OWASP ZAP
- ModSecurity
- Apache Web Server
- Kali Linux
- Ubuntu Server

---

## 👤 Author
Oluwaseun Quadri  
Cybersecurity Student  
