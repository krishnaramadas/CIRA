# 🎯 CIRA — Cost Intelligence Response Assistant

> A GCP cost intelligence platform powered by a custom MCP server — combining a visual spend dashboard with an AI chat assistant for conversational cost analysis, anomaly detection, and month-end forecasting. No data dumps. No pipelines. Live API calls only.

![Status](https://img.shields.io/badge/Status-In%20Development-orange)
![Platform](https://img.shields.io/badge/Platform-GCP-4285F4?logo=google-cloud)
![MCP](https://img.shields.io/badge/MCP-Custom%20Server-green)
![UI](https://img.shields.io/badge/UI-Streamlit-red?logo=streamlit)

---

## 🧩 What is CIRA?

CIRA goes beyond a static dashboard. It combines **visual cost intelligence** with an **embedded AI chat assistant** — letting engineers ask billing questions in plain English and get real answers backed by live GCP data.

### What CIRA can do that a dashboard can't:
- 💬 *"Why did Prod Dataflow costs spike on Wednesday?"*
- 🚨 *"Flag anything unusual vs last month"*
- 📈 *"We're 18 days in — will we exceed budget this month?"*
- 🔍 *"Which BigQuery datasets are the most expensive this quarter?"*
- 📊 *"Compare Dev vs QA vs Prod spend this sprint"*

---

## 🏗️ Architecture

```
GCP Projects (Dev / QA / Prod)
        ↓
Custom MCP Server (Python)
├── get_total_spend(period)
├── get_spend_by_project(project_id, period)
├── get_spend_by_service(service, period)
├── get_spend_by_environment(env, period)
├── get_daily_cost_trend(project_id)
├── detect_cost_anomalies(threshold)
└── forecast_month_end_spend(project_id)
        ↓
Claude API (generates natural language answers)
        ↓
Streamlit Web App
├── Dashboard
│   ├── Total spend (overview card)
│   ├── By environment (Dev / QA / Prod)
│   ├── By GCP service (Dataflow, Composer, BigQuery, GCS...)
│   ├── Cost trends over time
│   └── Anomaly flags
└── Embedded Chat Popup
    (ask anything — answers grounded in live API data)
```

**No BigQuery exports. No data pipelines. MCP server makes live GCP Billing API calls per request.**

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Cost Data Source | GCP Cloud Billing API (live calls) |
| AI Protocol | Model Context Protocol (MCP) |
| MCP Server | Python (custom built) |
| LLM | Claude API |
| Dashboard + Chat | Streamlit |
| Anomaly Detection | Statistical analysis over API data |
| Forecasting | Time-series projection over billing trends |

---

## 🤖 Three AI Capabilities

### 1. 💬 Conversational Cost Chat
Use the embedded chat popup in the Streamlit dashboard. Ask any billing question in natural language — CIRA makes live API calls and returns real answers with numbers.

### 2. 🚨 Anomaly Detection
CIRA automatically compares current spend against historical averages via the Billing API. Flags anything that deviates significantly — by project, by service, or by resource.

### 3. 📈 Month-End Forecasting
Given the current daily burn rate, CIRA projects end-of-month spend and flags whether you're on track or heading for a budget overrun.

---

## 🚀 Project Status

- [x] Architecture design
- [x] MCP server tool design
- [ ] GCP Billing API integration
- [ ] MCP server implementation
- [ ] Anomaly detection logic
- [ ] Forecasting module
- [ ] Streamlit dashboard + embedded chat
- [ ] Demo video

---

## 💡 Why MCP?

Traditional cost dashboards are static — you see what someone decided to show you. MCP turns cost data into a **live, queryable AI tool**. The MCP server handles all data fetching via live API calls — the Streamlit app consumes it for both the visual dashboard and the chat popup. One source of truth, one unified interface.

---

## 👤 Author

**Krishna Ramadas** — Senior Data Engineer
4+ years of GCP and Snowflake cost optimisation experience, including $250K+ in documented savings for a Fortune 500 client.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Krishna%20Ramadas-blue?logo=linkedin)](https://www.linkedin.com/in/krishna-ramadas-0807121b0/)
[![GitHub](https://img.shields.io/badge/GitHub-krishnaramadas-black?logo=github)](https://github.com/krishnaramadas)

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.


## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
