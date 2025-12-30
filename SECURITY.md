# 🔐 Security Policy — PhishSim-Pro

## Purpose

PhishSim-Pro is designed as an **ethical phishing simulation and security awareness platform**.  
The purpose of this project is to help organizations evaluate and improve employee resilience against **email-based social engineering attacks** within **authorized environments only**.

This project is **not intended for malicious use**.

---

## ✅ Authorized Usage Only

Use of this platform is permitted only under the following conditions:

- Explicit written authorization from the organization
- Internal security awareness training programs
- Red team / blue team simulations
- SOC and audit demonstrations
- Educational or lab-based cybersecurity research

Any use outside these boundaries is considered **unauthorized**.

---

## 🛡️ Data Handling Policy

### ✔️ Data That May Be Collected

The platform is intentionally designed to collect **limited, non-sensitive data**:

- Employee ID (organizational identifier)
- Name
- Department
- Work email address
- User-submitted comments
- Timestamp of interaction
- Campaign reference ID

### ❌ Data That Is Explicitly NOT Collected

To ensure ethical compliance, the platform does **not** capture:

- Passwords or login credentials
- Multi-factor authentication codes
- Financial information
- Government-issued identifiers
- Session tokens or cookies
- Browser fingerprinting data

---

## 🗄️ Storage & Retention

- All collected data is stored in controlled spreadsheets (Google Sheets / Excel)
- Data retention periods must be defined by the deploying organization
- It is recommended to purge campaign data after analysis is completed
- Access to tracking sheets should be restricted to **security administrators only**

---

## 📧 Email Safety Controls

- Emails are sent using authorized SMTP or Gmail API accounts
- Campaign execution is **manual and intentional**
- No autonomous propagation or worm-like behavior is implemented
- Rate limiting is recommended to avoid spam classification
- All email templates should clearly fall within simulation scope

---

## 🌐 Landing Page Security

- Landing pages are hosted via n8n webhooks
- Pages do not execute external scripts by default
- No third-party trackers or hidden analytics are embedded
- Form submissions are processed server-side via webhook pipelines

---

## 📝 Logging & Telemetry

- Campaign execution logs are limited to **operational metadata only**
- No keystroke logging is implemented
- No background activity capture
- Timestamps are used solely for awareness metrics and reporting

---

## 🛠️ Responsible Disclosure

If you discover a vulnerability or security weakness within this project:

- Do not exploit it
- Do not disclose it publicly without authorization
- Report it responsibly to the repository owner

---

## ⚖️ Legal & Compliance Considerations

Users deploying this platform must ensure compliance with:

- Organizational security policies
- Applicable data protection laws
- Email communication regulations
- Internal audit and risk management requirements

The author assumes **no liability for misuse** of this project.

---

## 🧭 Security Philosophy

PhishSim-Pro follows these principles:

- Least Data Collection
- Explicit Authorization
- Transparency in Simulation
- Audit-Friendly Design
- Education Over Exploitation

---

Maintained by **Sushil Shinde**  

