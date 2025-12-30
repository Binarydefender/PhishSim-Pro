# 🧩 n8n Workflows Overview — PhishSim-Pro

This directory contains the exported **n8n automation workflows** used in PhishSim-Pro.

Each workflow is designed to be **modular, auditable, and manually triggered** to ensure ethical simulation control.

---

## 1️⃣ Phishing Email Campaign  
**File:** phishing-email-campaign.json

### 🎯 Purpose
Send **phishing simulation emails** to employees and track delivery status.

### 📜 Flow Summary

- read employee data from **Google Sheets / Excel**
- loop through each employee record
- generate campaign-specific link
- send email using **Gmail API / SMTP**
- append delivery status & timestamp to tracking sheet

### ⏩ Trigger
- **manual execution only**
- prevents accidental or unauthorized campaigns

---

## 2️⃣ Landing Page Host  
**page**
<img width="1208" height="2225" alt="n8n ethika online_webhook_employee-appreciation-form" src="https://github.com/user-attachments/assets/9898c5e7-5335-4a27-aa92-e1ef8ddcd522" />


### 🎯 Purpose
Serve a **phishing simulation landing page** without running a separate web server.

### 📜 Flow Summary

- webhook receives **HTTP GET request**
- responds with **static HTML page**
- supports campaign theming and message customization

### 🔐 Security Characteristics

- no external JavaScript trackers
- no third-party analytics
- no credential harvesting fields

---

## 3️⃣ Form Capture & Tracking  
**Sheet-Captured data**
<img width="1765" height="494" alt="image" src="https://github.com/user-attachments/assets/4f4da1ae-2813-454e-83c8-e425a5c9bcbb" />


### 🎯 Purpose
Capture **controlled user interaction data** for awareness metrics.

### 📜 Flow Summary

- webhook receives **HTTP POST form submission**
- process only predefined fields
- attach server-side timestamp
- append submission record to **Google Sheets**
- return simulated success or awareness message

---

## 🛠️ Technologies Used

- n8n automation workflows  
- Gmail API / SMTP  
- Google Sheets / Excel  
- HTTP Webhooks  
- HTML landing page content  

---

## ⚠️ Ethical Use Reminder

These workflows are intended **only for authorized security awareness simulations**.

- manual trigger required
- limited data collected
- campaign scope restricted
- no credential harvesting

---

## 📎 Notes

- workflows are exported in **JSON format**
- import directly into n8n via **Import from File**
- modify templates safely before deployment
- maintain audit logs of campaign executions

