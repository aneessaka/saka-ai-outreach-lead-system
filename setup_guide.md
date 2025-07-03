# 🛠️ SAKA.AI Setup Guide

Welcome to the official setup guide for **SAKA.AI** — a fully automated, AI-powered cold outreach system built using GPT-4, Make.com, Google Sheets, and Gmail.

This guide will help you:
✅ Install the system  
✅ Customize it to your audience  
✅ Run it reliably with no-code tools

---

## 📦 Requirements

| Tool             | Use                                  | Link                                |
|------------------|---------------------------------------|-------------------------------------|
| **Make.com**     | No-code automation engine             | https://make.com                    |
| **Apify**        | Scrapes leads from Apollo             | https://apify.com                   |
| **OpenAI**       | GPT-4-powered personalization         | https://platform.openai.com         |
| **Google Sheets**| Lead management + status tracking     | https://sheets.google.com           |
| **Gmail**        | Sends cold emails                     | https://gmail.com                   |
| *(Optional)* **Instantly** | Email warmup + inbox scaling | https://instantly.ai                |

---

## 📋 System Overview

SAKA.AI follows this workflow:

1. Scrape leads from Apollo → Add to Sheet  
2. Loop each lead → Generate research via GPT  
3. Write email → Send via Gmail  
4. Track status in Google Sheet  
5. (Optional) Follow-up or reply detection logic

---

## ✅ STEP-BY-STEP INSTALLATION

---

### 1️⃣ Setup Google Sheet

Copy the template CSV or create a sheet with these **exact columns**:
First Name | Last Name | Company | Job Title | Company Website | Research | Email Address | LinkedIn URL | Personalized Message | Row | Sent | Sent At | Status



> 📌 Recommended: Freeze header row, set sharing to "Anyone with link" (Viewer/Editor depending on your use)

---

### 2️⃣ Import the Make.com Scenario

- Open Make.com → Go to “Scenarios” → Import Blueprint  
- Upload: `/blueprints/outreach_flow.json`  
- Connect required modules:
  - Google Sheets (Read, Update)
  - OpenAI (GPT)
  - Gmail (Send Email)
  - Apify (optional scraping)
- Set your variables (Row = index, message fields = GPT response)

> 🔒 Tip: Add delays between modules to avoid rate limits

---

### 3️⃣ Add the GPT Prompts

Go to the following steps inside your Make scenario:

| Step Name           | Use File                              |
|---------------------|----------------------------------------|
| GPT Research 1      | `/prompts/prospect_research.md`        |
| GPT Research 2      | `/prompts/company_research.md`         |
| GPT Email Writer    | `/prompts/personalized_email.md`       |

💡 GPT variables used:  
`{{first_name}}, {{job_title}}, {{company}}, {{linkedin_url}}, {{company_website}}, etc.`

---

### 4️⃣ Add Filters to Control Flow

Set filters before sending:

| Field   | Filter Logic                        |
|---------|-------------------------------------|
| `Sent`  | must be empty OR false              |
| `Email Address` | must exist (is not empty)   |
| `Personalized Message` | is not empty         |

> 📌 This prevents duplicates or incomplete records from being sent

---

### 5️⃣ Run and Test

1. Hit "Run once" to test with a single lead  
2. Check:
   - GPT outputs clean content  
   - Email is sent successfully  
   - Status + timestamp updated in Sheet

3. Once verified, schedule the scenario to run:
   - Every 4–6 hours (recommended)
   - Add error handlers for long runs

---

## ⚙️ Optional Upgrades

| Feature              | Description                          |
|----------------------|--------------------------------------|
| ✅ Follow-up Engine   | Send 1–2 emails after X days         |
| ✅ Inbox Rotation     | Rotate multiple Gmail accounts       |
| ✅ Reply Detection    | Use Gmail "watch thread" module      |
| ✅ LinkedIn Outreach  | Add PhantomBuster via webhook        |
| ✅ CRM Integration    | Push replies to HubSpot/Pipedrive    |
| ✅ Dashboard          | Track sent/open/reply via Data Studio|

---

## 🧪 Common Issues & Fixes

| Issue                      | Fix                                      |
|----------------------------|------------------------------------------|
| GPT prompt errors          | Check variable placeholders              |
| Sheet not updating         | Re-authorize Make access                 |
| Skipping rows              | Check filters, add 1s delay before loop  |
| Email not sent             | Check Gmail module & connection status   |

---

## 💬 Support / Contact

- 🔗 [LinkedIn: @Anees](https://linkedin.com/in/yourprofile)  
- 📧 Email: youremail@example.com  
- 🌐 [saka.ai](https://saka.ai) *(coming soon)*

---

Built with ⚙️ GPT + Automation by [**SAKA.AI**] — cold outreach made intelligent.


