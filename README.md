# 🎯 CIRA — Cost Intelligence Response Assistant

> A GCP cost intelligence platform powered by a custom MCP server — enabling conversational cost analysis, real-time anomaly detection, and month-end spend forecasting across GCP projects. No data dumps. No pipelines. Pure live API calls.

![Status](https://img.shields.io/badge/Status-In%20Development-orange)
![Platform](https://img.shields.io/badge/Platform-GCP-4285F4?logo=google-cloud)
![MCP](https://img.shields.io/badge/MCP-Custom%20Server-green)
![UI](https://img.shields.io/badge/UI-Streamlit-red?logo=streamlit)

---

## 🧩 What is CIRA?

CIRA goes beyond a Power BI dashboard. It combines a **visual cost dashboard** with an **AI chat assistant** — letting engineers ask billing questions in plain English and get real answers backed by live GCP data.

### What CIRA can do that a dashboard can't:
- 💬 *"Why did Prod Dataflow costs spike on Wednesday?"*
- 🚨 *"Flag anything that looks unusual vs last month"*
- 📈 *"We're 18 days into the month — will we exceed budget?"*
- 🔍 *"Which BigQuery datasets are the most expensive this quarter?"*
- 📊 *"Compare Dev vs QA vs Prod spend this sprint"*

---

## 🏗️ Architecture

<img width="840" height="720" alt="ChatGPT Image Feb 25, 2026, 03_31_24 PM" src="https://github.com/user-attachments/assets/2801d630-aa6d-4992-a12b-02cc8de28020" />


**No BigQuery exports. No data pipelines. MCP server makes live API calls to GCP Billing API per request.**

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Cost Data Source | GCP Cloud Billing API (live calls) |
| AI Protocol | Model Context Protocol (MCP) |
| MCP Server | Python (custom built) |
| Chat Interface | Claude Desktop (via MCP) |
| Dashboard | Streamlit |
| Anomaly Detection | Statistical analysis over API data |
| Forecasting | Time-series projection over billing trends |

---

## 🤖 Three AI Capabilities

### 1. 💬 Conversational Cost Chat
Connect CIRA to Claude Desktop via MCP. Ask any billing question in natural language — CIRA makes live API calls and returns real answers with numbers.

### 2. 🚨 Anomaly Detection
CIRA automatically compares current spend against historical averages using the Billing API. Flags anything that deviates significantly — by project, by service, or by resource.

### 3. 📈 Month-End Forecasting
Given current daily burn rate, CIRA projects end-of-month spend and flags whether you're on track or heading for a budget overrun.

---

## 🚀 Project Status

- [x] Architecture design
- [x] MCP server tool design
- [ ] GCP Billing API integration
- [ ] MCP server implementation
- [ ] Anomaly detection logic
- [ ] Forecasting module
- [ ] Streamlit dashboard + embedded chat
- [ ] Claude Desktop MCP config
- [ ] Demo video

---

## 💡 Why MCP?

Traditional cost dashboards are static — you see what someone decided to show you. MCP turns cost data into a **live, queryable AI tool**. The same MCP server powers both Claude Desktop (for engineers who prefer chat) and the Streamlit dashboard (for visual consumers) — one source of truth, two interfaces.

---

## 👤 Author

**Krishna Ramadas** — Senior Data Engineer
4+ years of GCP and Snowflake cost optimisation experience, including $250K+ in documented savings for a Fortune 500 client.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Krishna%20Ramadas-blue?logo=linkedin)](https://www.linkedin.com/in/krishna-ramadas-0807121b0/)
[![GitHub](https://img.shields.io/badge/GitHub-krishnaramadas-black?logo=github)](https://github.com/krishnaramadas)

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
