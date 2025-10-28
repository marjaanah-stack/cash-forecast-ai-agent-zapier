# 💷 Cash Forecast AI Agent (Zapier) — Full Stack

> **Apps:** Google Sheets · ChatGPT (OpenAI) · Slack · Google Slides · Google Drive · Notion  
> **Mode:** DRY_RUN=TRUE (safe test mode, drafts only)  
> **Region:** UK (GBP, UK spelling)

![Demo](docs/demo.gif)

This Agent automates short-term cash forecasting.  
It reads transactions from Google Sheets, generates a CFO-style forecast narrative with ChatGPT, creates a Google Slides deck, exports it to PowerPoint, posts a Slack summary, and logs the run to Notion.

---

## 🗂️ Repository Structure

cash-forecast-ai-agent-zapier/
├─ data/
│ ├─ transactions.csv # sample cash movement data
│ ├─ controls.csv # DRY_RUN, forecast horizon, Slack channel
│ └─ slides_template.csv # text blocks for presentation generation
├─ docs/
│ ├─ ARCHITECTURE.md
│ ├─ SETUP.md
│ ├─ AGENT_INSTRUCTIONS.md
│ ├─ TROUBLESHOOTING.md
│ ├─ demo.gif
│ └─ screenshots/
│ ├─ 01-sheets-transactions.png
│ ├─ 02-agent-tools.png
│ ├─ 03-agent-trigger.png
│ ├─ 04-instructions-panel.png
│ ├─ 05-test-run.png
│ ├─ 06-gmail-draft.png
│ ├─ 07-drive-export.png
│ ├─ 08-slides-presentation.png
│ ├─ 09-notion-log.png
│ └─ 10-slack-summary.png
└─ README.md

---

## ⚙️ How It Works

1. **Read data** → From Google Sheets (`transactions`, `controls`).
2. **Forecast** → ChatGPT computes 14-day forward cash flow.
3. **Narrate** → GPT generates drivers, risks & recommendations.
4. **Visualise** → Creates Google Slides deck → Drive export `.pptx`.
5. **Notify** → Posts Slack summary to `#finance-updates`.
6. **Log** → Notion database entry with forecast & links.
7. **Write back** → Updates `forecast_output` tab in the Sheet.

---

## 📊 Visual Flow

### 1️⃣ Google Sheets — Tabs  
Show the three tabs (`transactions`, `controls`, `forecast_output`) or combine them into one image.  
![Sheets](docs/screenshots/01-sheets-transactions.png?raw=true)

### 2️⃣ Zapier Agent — Tools  
Tools panel with connected apps:  
Google Sheets · ChatGPT · Slack · Google Slides · Google Drive · Notion  
![Tools](docs/screenshots/02-agent-tools.png?raw=true)

### 3️⃣ Zapier Agent — Trigger  
Agent trigger configured to **On demand** (or a schedule).  
![Trigger](docs/screenshots/03-agent-trigger.png?raw=true)

### 4️⃣ Zapier Agent — Instructions Panel  
The *“Instructions to follow”* section with your full Cash Forecast prompt visible.  
![Instructions](docs/screenshots/04-instructions-panel.png?raw=true)

### 5️⃣ Zapier Agent — Test Run / Activity  
Shows the workflow firing: Sheets → ChatGPT → Slides → Drive → Notion → Slack.  
![Run](docs/screenshots/05-test-run.png?raw=true)

### 6️⃣ Gmail — Draft (if enabled)  
A draft email with the generated forecast narrative (DRY_RUN mode).  
![Gmail](docs/screenshots/06-gmail-draft.png?raw=true)

### 7️⃣ Google Drive — Export File  
Drive action configured for `Microsoft PowerPoint (.pptx)` export.  
![Drive](docs/screenshots/07-drive-export.png?raw=true)

### 8️⃣ Google Slides — Presentation  
Shows the created deck populated with forecast summary.  
![Slides](docs/screenshots/08-slides-presentation.png?raw=true)

### 9️⃣ Notion — Database Log  
Displays the Notion entry created for the run (timestamp, summary, file link).  
![Notion](docs/screenshots/09-notion-log.png?raw=true)

### 🔟 Slack — Summary Message  
Slack post confirming completion and high-level forecast.  
![Slack](docs/screenshots/10-slack-summary.png?raw=true)

---

## 🧠 Agent Instruction Summary

Excerpt from [`docs/AGENT_INSTRUCTIONS.md`](docs/AGENT_INSTRUCTIONS.md):

> “You are Cash Forecast Agent. Read Google Sheets, generate 14-day forecast and narrative in GBP, post Slack summary, create Google Slides deck, export `.pptx`, log run to Notion, update sheet…”

---

## 🧩 Combining Sheet Tabs into One Screenshot

If you captured `tab1-transactions.png`, `tab2-controls.png`, and `tab3-forecast-output.png`,  
run this in Terminal:

```bash
cd ~/Downloads/cash-forecast-ai-agent-zapier/docs/screenshots
magick tab1-transactions.png tab2-controls.png tab3-forecast-output.png -append 01-sheets-transactions.png
Use +append instead of -append if you want them side-by-side.
🧾 Setup Summary
Import CSVs from /data into a new Google Sheet.
Connect Zapier → Google Sheets, ChatGPT, Slack, Slides, Drive, Notion.
Add tools in order and paste instructions from AGENT_INSTRUCTIONS.md.
Run manually once to test (DRY_RUN=TRUE).
Confirm:
Slack message posted
Slides deck created
PPTX exported to Drive
Notion log created
Sheet forecast_output updated
🚑 Troubleshooting
Issue	Fix
Screenshot doesn’t render	Append ?raw=true to its link.
“magick: not found”	Install ImageMagick via Homebrew: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" then brew install imagemagick.
PPTX missing	Ensure Drive Export File step uses Microsoft PowerPoint (.pptx).
Notion not updating	Reconnect Notion API key or database permissions.
🧰 Optional Automations
Add-on	Purpose
Slack slash command	Trigger forecast run from Slack.
Daily schedule	Auto-run at 8am every weekday.
Gmail send step	Send the exported PPTX to CFO.
🪄 Example Output
Slack Summary:
“Cash Forecast Agent run — 2025-09-24
Forecast generated for 14 days ahead.
Opening £45,000 → Closing £49,800 (+£4.8k).
PPTX + Notion log created. DRY_RUN=TRUE.”
Google Slides:
A 4-slide presentation with:
Summary
Drivers
Risks
Recommendations
🪶 License
MIT © 2025 Marjaana Peeters
