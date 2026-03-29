# 🔐 Vulnerability Assessment – OWASP Juice Shop

## 📌 Project Overview

This repository contains a **Vulnerability Assessment Report** conducted on the intentionally vulnerable web application **OWASP Juice Shop**.

The objective of this assessment was to identify common web security misconfigurations and publicly visible weaknesses using **passive security testing techniques** and industry-standard tools.

The assessment was performed as part of a cybersecurity training project with **Future Interns**.

---

## 🎯 Target Application

OWASP Juice Shop (local testing environment)

Target URL:

http://10.6.6.12:3000

---

## 🎯 Scope of Assessment

The assessment focused only on **publicly accessible components** of the application.

Allowed testing activities included:

* Passive vulnerability scanning
* Security header analysis
* Service enumeration

The following activities were **not performed**:

* Exploitation of vulnerabilities
* Brute-force attacks
* Denial of Service (DoS)
* Authentication bypass

---

## 🛠 Tools Used

The vulnerability assessment was conducted using the following tools:

* **Nmap** – used for port scanning and service discovery
* **OWASP ZAP** – used for passive web vulnerability scanning
* **Browser Developer Tools** – used to inspect HTTP headers and cookie configuration

---

## 🔎 Assessment Methodology

The security testing process followed these phases:

1. Service discovery using Nmap
2. Passive vulnerability scanning using OWASP ZAP
3. Analysis of HTTP headers and cookies using Browser DevTools
4. Documentation and risk classification of findings

The methodology follows general principles inspired by the **OWASP Web Security Testing Guide**.

---

## 📊 Summary of Findings

The passive scan identified several security issues mostly related to **security headers, cookie configuration and information disclosure**.

| Severity Level   | Number of Findings |
| ---------------- | ------------------ |
| 🟠 Medium        | 3                  |
| 🟡 Low           | 4                  |
| 🔵 Informational | 6                  |

These issues do not necessarily lead to immediate exploitation but they **increase the attack surface** of the web application.

---

## 🚨 Key Vulnerabilities Identified

### Content Security Policy (CSP) Header Not Set

Missing CSP protection may allow attackers to inject malicious scripts into the application.

### Cross-Domain Misconfiguration

Improper CORS configuration could allow cross-origin requests to access sensitive resources.

### Cookie Without SameSite Attribute

Cookies missing the **SameSite attribute** may increase the risk of Cross-Site Request Forgery (CSRF).

### X-Content-Type-Options Header Missing

The absence of the `X-Content-Type-Options: nosniff` header may allow MIME-sniffing attacks.

### Server Information Disclosure

HTTP response headers reveal information about the underlying server technology.

---

## 🛡 Security Recommendations

To improve the overall security posture of the application, the following measures are recommended:

### Implement Security Headers

Configure the following headers on the web server:

* Content-Security-Policy
* X-Frame-Options
* X-Content-Type-Options
* Strict-Transport-Security

### Improve Cookie Security

Ensure that all cookies include secure attributes:

* Secure
* HttpOnly
* SameSite

### Reduce Information Disclosure

Disable unnecessary server headers to prevent technology exposure.

---

## 📄 Full Report

The complete vulnerability assessment report is available in this repository:

```
/report/Vulnerability_Assessment_Report.pdf
```

The report contains:

* detailed vulnerability analysis
* evidence screenshots
* risk classification
* remediation recommendations

---

## ⚖️ Ethical Notice

This security assessment was conducted:

* For **educational purposes**
* Using an **intentionally vulnerable application**
* Without exploiting the discovered vulnerabilities

No harmful activity was performed during the testing process.

---

## 👤 Author

**Mahamat ADAM ADAM**
