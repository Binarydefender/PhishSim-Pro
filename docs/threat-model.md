# 🛡️ Threat Model — PhishSim-Pro (High Level)

## 🎯 Objective

To identify and control risks associated with running **authorized phishing simulations** while preventing:

- misuse of the platform  
- unauthorized campaign execution  
- data leakage  
- over-collection of personal data  

This threat model focuses on **ethical operation and safety controls**.

---

## 📌 In-Scope Components

The following components are considered within the security boundary:

- Gmail API (email delivery)
- Google Sheets (target list and tracking)
- n8n automation workflows
- Webhook-hosted landing pages

---

## 🚫 Out-of-Scope by Design

The system is **not intended** for the following activities:

- password harvesting
- credential validation
- browser fingerprinting
- third-party tracking
- external analytics platforms

These exclusions enforce **ethical simulation limits**.

---

## ⚠️ Identified Risks & ✔️ Controls

| Risk | Control |
|------|--------|
| Unauthorized email campaigns | Manual workflow execution only |
| Excessive data capture | Limited, predefined form fields |
| Credential misuse | No password fields implemented |
| Data leakage | Access-restricted Google Sheets |
| Email abuse / spam | Gmail API quotas and rate limits |
| Unauthorized changes to workflows | Role-based access & n8n credentials |
| Link misuse outside campaign | Campaign reference ID validation |

---

## 🔐 Data Protection

- Only **work email and awareness-related inputs** collected  
- All data stored in **Google Sheets / Excel** owned by organization  
- Data retention defined by **organizational policy**  
- Data access restricted to **security admins / awareness team**  

No collection of:

- authentication secrets  
- financial identifiers  
- government identity data  

---

## 🛡️ Security Posture Summary

The platform enforces:

- least data collection
- explicit authorization for campaign execution
- transparent simulation boundaries
- manual operator control
- simple & auditable data storage
- clear separation between simulation and credential collection

---

## ✅ Ethical Guardrails

PhishSim-Pro intentionally:

- does **not** harvest credentials  
- does **not** simulate account login validation  
- does **not** perform covert monitoring  
- does **not** use intrusive browser tracking  

Simulation purpose is **education over exploitation**.

---

## 📎 Conclusion

This threat model demonstrates that PhishSim-Pro:

- reduces risk of misuse  
- avoids collecting sensitive information  
- maintains auditability  
- protects participant privacy  
- enforces ethical simulation boundaries  

It is suitable for **authorized corporate security awareness programs** when operated within policy and legal frameworks.

