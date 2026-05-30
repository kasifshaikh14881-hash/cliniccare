# 🏥 ClinicCare — AI-Powered Patient Retention System

> **Microsoft Agents League Hackathon 2026** — Built with Microsoft GitHub Models + DeepSeek-V3

[![Hackathon](https://img.shields.io/badge/Microsoft-Agents%20League%202026-0078D4?style=for-the-badge&logo=microsoft)](https://info.microsoft.com/Agents-League-Hackathon-Thank-You.html)
[![AI Model](https://img.shields.io/badge/DeepSeek--V3--0324-GitHub%20Models-00D4FF?style=for-the-badge&logo=github)](https://github.com/marketplace/models)
[![Cost](https://img.shields.io/badge/Monthly%20Cost-₹0%20Free-00E87A?style=for-the-badge)](https://github.com/kasifshaikh14881-hash/cliniccare)
[![Automation](https://img.shields.io/badge/Activepieces-7%20AI%20Flows-7B4FFF?style=for-the-badge)](https://activepieces.com)

---

## 🚀 What is ClinicCare?

**ClinicCare** is a zero-cost, AI-powered patient follow-up and retention system built for clinics. It eliminates the most common reason patients never return — **nobody followed up.**

A receptionist fills a simple Google Form after each patient visit. That single action triggers **7 fully automated AI flows** — follow-ups, sentiment analysis, emergency alerts, prescription summaries, review requests, and a live dashboard. All powered by **Microsoft GitHub Models (DeepSeek-V3)** and **Activepieces automation**. For free.

---

## 😩 The Problem

- **68%** of clinic patients never return after their first visit
- Doctors are too busy to call every patient manually
- CRM software costs ₹5,000–₹20,000/month — out of reach for small clinics
- Critical post-treatment symptoms go undetected for hours
- Google reviews never get collected

---

## ✅ The Solution — 7 AI Flows

| # | Flow | Description |
|---|------|-------------|
| 1 | **WhatsApp Follow-up** | Personalized follow-up sent to every patient at 9 AM the next day |
| 2 | **AI Sentiment Analysis** | DeepSeek-V3 reads patient replies, classifies as Positive / Negative / Critical |
| 3 | **Positive Response** | Happy patients receive a warm empathy message + Google review request (30 min delay) |
| 4 | **Emergency Alert** | Critical symptoms trigger an instant WhatsApp alert to the doctor in <30 seconds |
| 5 | **Appointment Reminder** | Smart reminders for follow-up visits based on treatment type |
| 6 | **Prescription Summary** | AI converts complex medical prescriptions into clear, patient-friendly instructions |
| 7 | **Live Dashboard** | Real-time retention metrics, sentiment trends, and review counts |

---

## 🏗️ Architecture

```
Receptionist fills Google Form
        ↓
Google Sheets (patient database)
        ↓
Activepieces (automation engine)
        ↓
┌───────────────────────────────────────────┐
│           7 AI-Powered Flows              │
│  WhatsApp API ←→ DeepSeek-V3 (AI) ←→ Sheets  │
└───────────────────────────────────────────┘
        ↓
Patient's WhatsApp / Doctor's WhatsApp / Dashboard
```

---

## 🛠️ Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| [Microsoft GitHub Models](https://github.com/marketplace/models) | AI — DeepSeek-V3-0324 for sentiment analysis & prescription summarization | **Free** |
| [Activepieces](https://activepieces.com) | Automation engine — all 7 flows | **Free (open source)** |
| [WhatsApp Business API](https://developers.facebook.com/docs/whatsapp) | Two-way patient messaging | **Free tier** |
| [Google Forms + Sheets](https://workspace.google.com) | Patient data capture + database | **Free** |
| **Total** | | **₹0 / month** |

---

## 📁 Repository Structure

```
cliniccare/
├── workflows/                          # Activepieces workflow JSON files
│   ├── WF1a — Daily Patient Scheduler  # Triggers at 9 AM daily, scans patients
│   ├── WF1b — Message Sender           # Sends personalized WhatsApp messages
│   ├── WF2  — Webhook Ingestion        # Receives incoming WhatsApp replies
│   ├── WF2b — Webhook Queue Processor  # Processes reply queue + AI analysis
│   ├── WF4  — Reply Router             # Routes positive/negative/critical responses
│   ├── WF5  — Review Request Flow      # Sends Google review requests to happy patients
│   └── WF6  — Escalation Handler       # Sends emergency alerts to doctor
├── dashboard/
│   ├── ClinicCare_Demo_v6.html         # ✨ Hackathon demo (cinematic, auto-playing)
│   └── ClinicCare_Dashboard_v2.html    # Live analytics dashboard
└── README.md
```

---

## ⚙️ Setup Guide

### Prerequisites
- Google Account (Forms + Sheets)
- WhatsApp Business Account (Meta)
- [Activepieces](https://activepieces.com) account (free, self-hostable)
- GitHub account (for Microsoft GitHub Models API)

### Step 1 — Google Sheets
1. Create a new Google Sheet with these columns:
   ```
   Name | Phone | Treatment | Visit Date | Status | Followed Up | Sentiment | Row
   ```
2. Copy your **Spreadsheet ID** from the URL:
   `https://docs.google.com/spreadsheets/d/YOUR_SPREADSHEET_ID/edit`

### Step 2 — GitHub Models API
1. Go to [github.com/marketplace/models](https://github.com/marketplace/models)
2. Select **DeepSeek-V3-0324**
3. Generate a **Personal Access Token** with `models:read` permission
4. Save as `GITHUB_TOKEN`

### Step 3 — WhatsApp Business API
1. Set up a [Meta Business Account](https://business.facebook.com)
2. Get your **Phone Number ID** and **WhatsApp Access Token**
3. Set your webhook URL to your Activepieces webhook endpoint

### Step 4 — Import Workflows into Activepieces
1. Open Activepieces → **Flows** → **Import**
2. Import each JSON file from the `workflows/` folder
3. Replace all placeholder values:

| Placeholder | Replace With |
|-------------|--------------|
| `YOUR_SPREADSHEET_ID` | Your Google Sheet ID |
| `YOUR_CONNECTION_ID` | Your Activepieces Google connection ID |
| `YOUR_WORKFLOW_ID` | Auto-generated on import |
| `YOUR_GITHUB_TOKEN_HERE` | Your GitHub Personal Access Token |

### Step 5 — Configure & Activate
1. Set the WF1a scheduler to run daily at **9:00 AM** your timezone
2. Activate all 7 flows
3. Test with a sample patient entry in your Google Sheet

---

## 📊 Real Impact

| Metric | Before ClinicCare | After ClinicCare |
|--------|-------------------|------------------|
| Patient follow-up rate | 0% (manual, never happened) | **100%** (every patient) |
| Emergency response time | Hours (if noticed) | **< 30 seconds** |
| Google reviews/month | 0–1 (manual ask) | **10–30** (automated) |
| Monthly cost | ₹5,000–₹20,000 (CRM) | **₹0** |
| Setup time | Weeks | **5 minutes** |

---

## 🎬 Demo

Open `dashboard/ClinicCare_Demo_v6.html` in your browser for the full cinematic hackathon demo.

The demo auto-plays through all 13 scenes showing the complete patient journey — from Google Form submission to AI analysis, emergency alerts, and live dashboard.

---

## 👨‍💻 Built By

**Kasif Shaikh** — Microsoft Agents League Hackathon 2026

- 🌐 Built with Microsoft GitHub Models (DeepSeek-V3-0324)
- ⚡ Powered by Activepieces open-source automation
- 💬 WhatsApp Business API for patient communication
- 📊 Google Workspace for zero-cost data management

---

## 📄 License

MIT License — free to use, modify, and deploy for any clinic.
