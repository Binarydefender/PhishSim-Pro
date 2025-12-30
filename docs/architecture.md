# 🏗️ Architecture & Workflow Design — PhishSim-Pro

## 📌 Overview

PhishSim-Pro is built using a **modular, event-driven architecture** powered by **n8n**.  
Each major function of the phishing simulation lifecycle is isolated into **independent workflows** to ensure:

- clear separation of concerns  
- controlled execution  
- easy auditing and customization  
- minimal blast radius in case of errors  

The system consists of three primary workflows:

1. Phishing Email Campaign Execution  
2. Phishing Landing Page Hosting  
3. Form Submission Capture & Telemetry Logging  


## 🔧 High-Level System Architecture

**Data Source --> Workflow 1 --> Workflow 2 --> workflow 3**


## 📤 Workflow 1 — Phishing Email Campaign Execution

### 🎯 Purpose
To automate the **controlled sending** of phishing simulation emails to a predefined user list and track delivery status.

### ⏩ Trigger
- Manual execution inside n8n (“**Execute Workflow**”)
- Ensures **deliberate, authorized** campaign launch

### 🛠️ Steps

#### 1️⃣ Get Target Data
Reads employee records from:
- Google Sheets  

Typical fields:

- Employee ID  
- Name  
- Department  
- Work Email  

#### 2️⃣ Loop Over Items
- Iterates employee records one-by-one  
- Enables individual logging & control  

#### 3️⃣ Code Node
- Dynamically generates personalized email content  
- Injects **unique landing page URL + campaign reference ID**

#### 4️⃣ Send Phishing Campaign Email
- Uses **Gmail API**
- Email is designed for **awareness simulation only**

#### 5️⃣ Update Tracking Sheet
Stores:

- sent status  
- email address  
- timestamp  
- campaign identifier  

### 🔐 Security Controls

- ❌ no automated retries without review  
- ❌ no autonomous propagation  
- ✔ manual initiation required  

---

## 🌐 Workflow 2 — Phishing Landing Page Hosting

### 🎯 Purpose
To host a **custom phishing simulation landing page** without a dedicated web server.

### ⏩ Trigger
- HTTP **GET** request to **n8n webhook URL**
- Link embedded inside simulation email

### 🛠️ Steps

#### 1️⃣ Webhook — Display Form
- Listens for GET requests  
- Acts as landing page endpoint  

#### 2️⃣ Respond with HTML Page
- Serves static customizable HTML page

Supports customizing:

- branding & theme  
- message tone  
- simulated business scenario  
- form fields  

### 🛡️ Landing Page Characteristics

- No external JavaScript by default  
- No third-party tracking  
- No credential harvesting  
- Used purely for **awareness simulation**

---

## 📝 Workflow 3 — Form Submission & Telemetry Logging

### 🎯 Purpose
To capture **controlled user interaction** and generate measurable awareness metrics.

### ⏩ Trigger
- HTTP **POST** request from landing page form

### 🛠️ Steps

#### 1️⃣ Webhook — Submit Form
- Accepts form submissions  
- Only predefined allowed fields  

#### 2️⃣ Process Form Data
- validates & normalizes inputs  
- attaches server-side timestamp  
- adds campaign metadata  

#### 3️⃣ Append Row in Sheet
Stored into:

- Google Sheet

#### 4️⃣ Respond Success
- sends simulated confirmation / awareness message  
- ends user flow cleanly  

### 📊 Captured Telemetry

- Employee ID  
- Name  
- Department  
- Work email  
- User comments  
- Submission timestamp  

---

## 🔄 Data Flow Summary

Email Sent
→ Link Clicked
→ Landing Page Loaded
→ Form Submitted
→ Data Logged

No:

- ❌ background activity capture  
- ❌ keystroke logging  
- ❌ credential harvesting  

---

## 🧭 Design Principles

- Separation of Workflows  
- Least Data Collection  
- Webhook Isolation  
- Manual Campaign Control  
- Audit-Friendly Logging  

---

## 🚀 Extensibility & Future Enhancements

Supports future additions such as:

- campaign analytics dashboards  
- click-rate vs submission-rate metrics  
- integration with SIEM/SOC platforms  
- awareness scoring per department  
- automated PDF/Excel report generation  

---

## ✅ Conclusion

This architecture demonstrates a **real-world phishing simulation system** designed with:

- ethical constraints  
- operational safety controls  
- auditability  
- blue-team automation practices  

It aligns with enterprise **security awareness programs** and defensive cybersecurity maturity goals.
