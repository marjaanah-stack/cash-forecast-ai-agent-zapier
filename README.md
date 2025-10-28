# 💷 Cash Forecast AI Agent (Zapier) — Full Stack

> _An AI-powered CFO assistant automating short-term cash forecasting, visualisation, and reporting._  
> Built with **Zapier AI Agents**, **ChatGPT**, **Google Workspace**, **Slack**, and **Notion**.  
> Author: **Marjaana Peeters**

![Demo GIF](docs/demo.gif)

---

## 🧭 Overview

The **Cash Forecast AI Agent** automates a typical finance process:  
it reads transactional data from Google Sheets, generates a 14-day forecast and executive summary, creates a PowerPoint-ready report, posts updates to Slack, and logs results in Notion — all in one automated flow.

🧮 Google Sheets → 🤖 ChatGPT → 🎞️ Google Slides → 💾 Google Drive → 🧱 Notion → 💬 Slack

yaml
Copy code

**Purpose:**  
To showcase how a finance professional can combine _AI reasoning_ and _automation tools_ to produce CFO-level insights and outputs with minimal manual effort.

---

## ⚙️ Core Capabilities

| Function | Description |
|-----------|-------------|
| 📊 **Data Ingestion** | Reads cash transactions and controls from Google Sheets |
| 🧠 **Forecasting & Narration** | ChatGPT generates a 14-day cash forecast and commentary |
| 🪄 **Visualisation** | Builds a Google Slides presentation deck |
| 💾 **Export & Logging** | Exports the deck to PowerPoint (`.pptx`) and logs results in Notion |
| 💬 **Communication** | Posts summary to Slack (DRY_RUN mode for testing) |
| 🔒 **Safety** | DRY_RUN=TRUE by default — no real messages or sends |

---

## 🧩 Architecture at a Glance

1️⃣ Google Sheets (transactions, controls)
2️⃣ ChatGPT → generates forecast narrative
3️⃣ Google Slides → creates deck
4️⃣ Google Drive → exports to PPTX
5️⃣ Notion → logs the run
6️⃣ Slack → posts summary

yaml
Copy code

---

## 📸 Key Screenshots

### 1️⃣ Google Sheets — Data Tabs  
Transactions, controls, and forecast_output tabs combined  
![Sheets](docs/screenshots/01-sheets-transactions.png?raw=true)

### 2️⃣ Zapier Agent — Tools Configuration  
Tools connected: Sheets · ChatGPT · Slides · Drive · Notion · Slack  
![Tools](docs/screenshots/02-agent-tools.png?raw=true)

### 3️⃣ Zapier Agent — Instructions Panel  
The “Instructions to follow” panel showing the Cash Forecast logic  
![Instructions](docs/screenshots/04-instructions-panel.png?raw=true)

### 4️⃣ Zapier Agent — Run Activity  
Execution flow: rows read → forecast generated → Slides created → Drive exported → Notion logged → Slack posted  
![Run](docs/screenshots/05-test-run.png?raw=true)

### 5️⃣ Google Slides — Generated Deck  
Forecast presentation automatically populated from the Agent  
![Slides](docs/screenshots/08-slides-presentation.png?raw=true)

### 6️⃣ Slack — Summary Message  
Slack post summarising the forecast and confirming completion  
![Slack](docs/screenshots/10-slack-summary.png?raw=true)

---

## 🖼️ Full Screenshot Gallery

<details>
<summary>Click to view all steps</summary>

| Step | Screenshot |
|------|-------------|
| Agent Trigger | ![Trigger](docs/screenshots/03-agent-trigger.png?raw=true) |
| Gmail Draft (optional) | ![Gmail](docs/screenshots/06-gmail-draft.png?raw=true) |
| Drive Export | ![Drive](docs/screenshots/07-drive-export.png?raw=true) |
| Notion Log | ![Notion](docs/screenshots/09-notion-log.png?raw=true) |

</details>

---

## 🧾 Setup Summary

1. Import CSVs from `/data` into a new Google Sheet (`transactions`, `controls`, `forecast_output`).  
2. In Zapier → create a new **AI Agent** named _Cash Forecast Agent_.  
3. Connect: Google Sheets · ChatGPT (OpenAI API key) · Slack · Google Slides · Google Drive · Notion.  
4. Paste contents of [`docs/AGENT_INSTRUCTIONS.md`](docs/AGENT_INSTRUCTIONS.md) into the “Instructions to follow” box.  
5. Trigger: **On demand** (manual run).  
6. Run once to test. Confirm:
   - Slides deck created  
   - PPTX exported to Drive  
   - Notion log added  
   - Slack message posted  
   - Sheet updated  

---

🧠 Example Output
Slack Summary:

“Cash Forecast Agent run — 2025-09-24
Forecast generated for 14 days ahead.
Opening £45,000 → Closing £49,800 (+£4.8k).
PPTX + Notion log created. DRY_RUN=TRUE.”

Google Slides:

Four slides — Summary, Drivers, Risks, Recommendations.
Automatically populated via ChatGPT and Google Slides API.

🧰 Tech Stack
Layer	Tools
Data	Google Sheets
AI	ChatGPT (OpenAI API)
Workflow	Zapier AI Agents
Output	Google Slides + Drive
Collaboration	Slack
Logging	Notion

👩‍💼 Author
Marjaana Peeters
Finance Leader & AI-Native CFO in training
LinkedIn · GitHub
