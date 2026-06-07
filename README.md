# AI KPI Reporting System

> Automated weekly reporting pipeline that transforms raw business data into AI-generated executive insights — delivered every Monday without manual effort.

---

## Business Problem

A multi-channel restaurant chain generates data across multiple systems, including POS, CRM, advertising platforms, analytics tools, and loyalty programs.

Preparing a weekly executive report required manual consolidation, validation and interpretation of data every week, resulting in significant time investment and potential inconsistencies.

---

## Solution

An end-to-end automated reporting system that runs every Monday and delivers:

* AI-generated executive summaries with key risks and recommendations
* Interactive dashboards updated automatically
* Structured Telegram notifications with key business signals

---

## Outcomes

* ⏱️ Weekly reporting process fully automated
* 📊 KPIs from 5+ business systems consolidated into a single reporting pipeline
* 🤖 AI-generated insights replace repetitive manual analysis
* 📱 Executive stakeholders receive structured reports automatically every Monday

---

## Architecture

```text
Data Sources
(POS · CRM · GA4 · Google Ads · Meta Ads · ASA · SEO · SMS)
        ↓
ETL Layer
Google Sheets
(IMPORTRANGE · QUERY · ARRAYFORMULA)
        ↓
Weekly KPI Vitrine
(executive_summary)
        ↓
n8n Automation
(scheduled every Monday)
        ↓
Claude AI Analysis
(JSON contract · prompt engineering)
        ↓
├── Interactive Dashboard (Cloudflare Workers)
└── Telegram Notification (summary + link)
```

---

## Key Design Decisions

### Claude doesn't generate numbers

All metrics originate from source systems. AI is responsible for interpretation, prioritization and insight generation only.

### Paid ROAS vs Total ROAS

Offline (dine-in) revenue represents a significant share of total sales but cannot be reliably attributed to paid media. The system therefore uses delivery-only ROAS to avoid misleading performance conclusions.

### Rolling 12-Week Window

Provides sufficient trend context while automatically excluding incomplete current-week data.

### Structured JSON Contract

AI responses follow a predefined schema, enabling deterministic dashboard rendering and eliminating fragile text parsing logic.

---

## Technology Stack

| Layer      | Technology                                         |
| ---------- | -------------------------------------------------- |
| Data       | Google Sheets · Windsor.ai · Google Ads Add-on     |
| ETL        | IMPORTRANGE · QUERY · ARRAYFORMULA · GOOGLEFINANCE |
| Automation | n8n                                                |
| AI         | Claude Opus (Anthropic API)                        |
| Dashboard  | HTML · Chart.js · Cloudflare Workers               |
| Delivery   | Telegram Bot API                                   |

---

## Documentation

*Detailed technical documentation coming soon.*

---

## Project Status

✅ Data Layer
✅ ETL Pipeline
✅ n8n Automation
✅ Claude AI Analysis
✅ Interactive Dashboard
✅ Telegram Delivery
✅ Production Deployment

---

*Built for a Ukrainian restaurant chain. Client data anonymized.*
