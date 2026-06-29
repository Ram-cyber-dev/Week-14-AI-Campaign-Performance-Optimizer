# 🎯 AI Campaign Performance Optimizer — Self-Running D2C System

Runs at 9 AM every day. No human trigger. Reads your ad data, makes decisions, rewrites creatives, detects anomalies, predicts fatigue, and delivers a premium brief to your inbox — while you slept.


## 🎯 What Makes This Different

Every project until Week 14 required a human to fill a form. **This one runs itself — forever.**

- No form. No button press. Just time.
- Reads yesterday's campaign data from Google Sheets
- Makes SCALE / PAUSE / REFRESH / MAINTAIN decisions
- Has **memory** — remembers last week's decisions to detect trends
- Delivers brief + Telegram alert every morning automatically


## 🤖 What It Does Daily

1. **Reads campaign data** from Google Sheets (Meta/Google Ads export)
2. **Computes metrics** — ROAS, CTR, CPC, CPA, budget utilization per campaign
3. **Aggregates portfolio** — sees the whole account, not just individual campaigns
4. **Reads decision history** — remembers past 7 runs for trend detection
5. **Computes week-over-week trends** — accelerating / decelerating / flat
6. **Agent 3: Anomaly Detector** — catches hidden issues (broken pixels, audience fatigue, budget pacing)
7. **Agent 1: Performance Analyst** — SCALE/PAUSE/REFRESH/MAINTAIN with exact reasoning
8. **Agent 2: Creative Rewriter** — fresh copy for fatiguing ads
9. **Creative Fatigue Predictor** — predicts which creatives will die before they do
10. **Spend Anomaly Alert** — detects wasted spend and portfolio health score
11. **Weekly Performance Summary** — executive verdict, top win, biggest risk, budget recommendation
12. **Budget Reallocation Calculator** — exact ₹ moves between campaigns
13. **Sends premium HTML email brief** to brand owner
14. **Fires Telegram alert** with key decisions
15. **Logs every decision** to history for tomorrow's memory


## 🏗️ Architecture (27 nodes)

9AM Trigger → Read Campaigns → Compute Metrics → Aggregate Portfolio →
Read Decision History → Compute Trends → Build Anomaly Prompt →
Agent3:Anomaly Detector → Parse Anomalies → Build Analyst Prompt →
Agent1:Performance Analyst → Parse Decisions → Build Rewrite Prompt →
Agent2:Creative Rewriter → Parse Rewrites →
Creative Fatigue Predictor → Parse Fatigue →
Spend Anomaly Alert → Parse Anomalies →
Weekly Performance Summary → Parse Summary →
Budget Reallocation → Build Brief →
Email to Owner + Telegram Alert + Log to History


## ⚙️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Automation + Scheduler | n8n (self-hosted) |
| All 3 AI Agents | GPT-4o-mini |
| Enhancement Agents | GPT-4o-mini |
| Campaign Data | Google Sheets |
| Decision Memory | Google Sheets |
| Email Delivery | Gmail API |
| Instant Alerts | Telegram Bot |


## 🚀 Key Features

- **27 nodes** — self-running, no human trigger
- **Memory system** — reads 7-run history to detect trends
- **3 AI agents** in sequence — anomaly → analyst → rewriter
- **Creative Fatigue Predictor** — days until fatigue, lifespan score
- **Spend Anomaly Alert** — portfolio health score, wasted spend estimate
- **Weekly Performance Summary** — executive verdict for brand owner
- **Budget Reallocation** — exact ₹ moves computed automatically
- **Dual delivery** — HTML email + Telegram alert


## 💡 Business Case

Every D2C brand wastes 20-30% of ad budget on underperforming campaigns.  
This catches it daily.  
**Worth ₹15-25K/month retainer per client — paid by the budget it recovers.**

Also works for: HVAC/plumbing Google Ads, real estate Meta ads, any lead-gen business running paid campaigns.


## 🔧 Setup

1. Import `AI_Campaign_Performance_Optimizer.json` into n8n
2. Configure credentials:
   - **OpenAI** — API key (gpt-4o-mini access required)
   - **Gmail** — OAuth2
   - **Google Sheets** — OAuth2
   - **Telegram** — Bot token from @BotFather
3. Create Google Sheet: **"AI Campaign Performance Optimizer"** with 2 tabs:

**Tab 1: `Campaigns`**
`Campaign Name, Platform, Status, Daily Budget, Spend, Impressions, Clicks, Conversions, Revenue, Target ROAS, Headline, Primary Text, Yesterday Spend, Yesterday Revenue, Days Running, Creative`

**Tab 2: `Decision_History`**
`Date, Campaign, Platform, ROAS, CTR, CPA, Spend, Revenue, Action, Reason, Step, Priority, New Headline, New Copy`

4. Paste your daily Ads Manager CSV export into the Campaigns tab
5. Update Telegram Chat ID in the Telegram Alert node
6. The 9 AM trigger runs automatically — or hit Execute to test manually


## 🎬 Demo Data

7 GlowVeda campaigns across Meta and Google — Diwali Serum Retargeting, Gold Radiance Prospecting, Vitamin C Awareness, and more. Portfolio spend ₹13,020, revenue ₹45,580, portfolio ROAS 3.5x.


## 👤 Author

Built by Ram
Founder, MissedCallRecovery.org — AI voice receptionist 
platform for US plumbing and HVAC businesses
Available for freelance AI automation projects
Building done-for-you AI systems for D2C brands and service businesses  
[GitHub](https://github.com/Ram-cyber-dev)
