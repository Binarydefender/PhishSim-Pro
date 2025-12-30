# PhishSim-Pro
### Phishing Simulation & Security Awareness Automation Platform

PhishSim-Pro is an ethical phishing simulation platform built using n8n automation workflows to help organizations assess and improve employee awareness against email-based social engineering attacks.

The platform automates phishing campaigns, hosts customizable landing pages, captures controlled user interactions, and records telemetry for:

- security awareness training
- SOC reporting
- audit readiness
- red-team and blue-team exercises

⚠️ Important: This project is strictly intended for authorized security training and awareness purposes only. Unauthorized use is prohibited.

---

## 🚀 Key Capabilities

- Automated phishing campaign execution
- Target user ingestion from Google Sheets
- Customizable phishing landing pages via webhooks
- Secure form submission capture with timestamps
- Centralized campaign tracking and analytics
- Modular workflow design for rapid customization
- Supports multiple simultaneous campaigns

---

## 🏗️ High-Level Architecture

Employee List (Google Sheet)
        ↓
n8n Campaign Workflow
        ↓
Phishing Email Sent (SMTP / Gmail API)
        ↓
User Clicks Link
        ↓
Hosted Landing Page (Webhook + HTML)
        ↓
Form Submission
        ↓
Response Logging + Timestamp
        ↓
Tracking Sheet / Analytics

---

## ⚙️ Workflow Breakdown

### 1) Phishing Email Campaign Workflow

- Reads employee email IDs from spreadsheet
- Iterates through each record
- Sends controlled phishing simulation email
- Updates tracking sheet with delivery status

### 2) Phishing Landing Page Workflow

- Hosts a customizable HTML page via n8n webhook
- Displays simulated internal form
- Allows modification of fields without redeployment

### 3) Form Capture & Tracking Workflow

- Captures submitted form data
- Logs timestamp, campaign reference, and user inputs
- Appends records to response tracking sheet
- Returns success response to user

---

## 🧾 Data Collected (Controlled & Ethical)

### Collected
- Employee ID
- Name
- Department
- Work email
- User comments
- Submission timestamp

### Not Collected
- Passwords
- Authentication tokens
- Financial credentials
- Identity proof
- Sensitive personal data

---

## 🧰 Technologies Used

- Automation: n8n
- Email: SMTP / Gmail API
- Frontend: HTML, CSS, JavaScript
- Backend: Webhooks
- Data Storage: Google Sheets / Excel
- Security Domain: Phishing Simulation & Security Awareness

---

## 📁 Repository Structure

PhishSim-Pro/
├── README.md
├── SECURITY.md
├── workflows/
│   ├── phishing-email-campaign.json
│   ├── landing-page-host.json
│   └── form-capture-tracking.json
├── landing-page/
│   ├── index.html
├── docs/
│   ├── architecture.md
│   └── threat-model.md
├── sample-data/
│   ├── employee_template.xlsx
│   └── campaign_tracking_template.xlsx
└── LICENSE

---

## ⚖️ Ethical Use Disclaimer

This project is intended only for:

- internal security awareness programs
- red team simulations
- blue team defensive exercises
- educational demonstrations

Use only with:

- explicit written authorization
- proper organizational approval
- compliance with local laws and policies

Unauthorized use against individuals or organizations without consent is strictly prohibited.

---

## 👤 Author

Developed by **Sushil Shinde**  
(Security Automation | Cybersecurity Analyst)
