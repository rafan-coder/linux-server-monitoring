<div align="center">

# 📈 Grafana & Prometheus Infrastructure Monitoring

**Real-time Linux server monitoring with Prometheus, Node Exporter and Grafana.**

<img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white&labelColor=070D1A" />
<img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white&labelColor=070D1A" />
<img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white&labelColor=070D1A" />
<img src="https://img.shields.io/badge/WSL-0078D6?style=for-the-badge&logo=windows&logoColor=white&labelColor=070D1A" />

<br/>

<img src="https://img.shields.io/github/last-commit/rafan-coder/REPO-NAME?style=flat-square&color=5CD6F0&labelColor=070D1A" />
<img src="https://img.shields.io/github/repo-size/rafan-coder/REPO-NAME?style=flat-square&color=8F86FF&labelColor=070D1A" />
<img src="https://img.shields.io/badge/Status-Completed-5EE3A1?style=flat-square&labelColor=070D1A" />

</div>

---

## 🎯 Overview

This project sets up a complete monitoring stack for a Linux server. **Node Exporter** collects system metrics, **Prometheus** scrapes and stores them, and **Grafana** turns them into a live dashboard showing the health of the server.

## 🖼️ Dashboard Preview

<div align="center">

<img src="docs/dashboard.png" width="90%" alt="Grafana dashboard" />

<sub>Grafana dashboard tracking CPU, RAM, disk, network traffic and uptime.</sub>

</div>

## 🏗️ Architecture

```mermaid
%%{init: {'theme':'dark','themeVariables':{'primaryColor':'#0F1B33','primaryTextColor':'#E9EFFA','primaryBorderColor':'#5CD6F0','lineColor':'#8F86FF'}}}%%
flowchart LR
    A["Linux Server<br/>Node Exporter :9100"] -->|"exposes metrics"| B["Prometheus<br/>:9090"]
    B -->|"PromQL queries"| C["Grafana<br/>:3000"]
    C --> D(["Dashboard<br/>CPU · RAM · Disk · Network · Uptime"])
```

## ✨ Features

| Metric | What it shows |
|---|---|
| 🧠 **CPU** | Usage across cores over time |
| 💾 **Memory** | Used vs available RAM |
| 🗄️ **Disk** | Space used per filesystem |
| 🌐 **Network** | Incoming and outgoing traffic |
| ⏱️ **Uptime** | How long the server has been running |

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| Ubuntu Linux (WSL) | Host environment |
| Node Exporter | Collects server metrics |
| Prometheus | Scrapes and stores time-series data |
| Grafana | Dashboards and visualization |

## 🚀 Setup

<details>
<summary><b>Click to expand setup steps</b></summary>

<br/>

**1. Start Node Exporter**
```bash
./node_exporter
# metrics available at http://localhost:9100/metrics
```

**2. Configure Prometheus** (`prometheus.yml`)
```yaml
scrape_configs:
  - job_name: "node"
    static_configs:
      - targets: ["localhost:9100"]
```

**3. Start Prometheus**
```bash
./prometheus --config.file=prometheus.yml
# UI at http://localhost:9090
```

**4. Open Grafana** at `http://localhost:3000`, add Prometheus as a data source (`http://localhost:9090`), then build or import the dashboard.

</details>

## 📁 Project Structure

```text
.
├── prometheus.yml      # Prometheus scrape config
├── docs/
│   └── dashboard.png   # Dashboard screenshot
└── README.md
```

## 📚 What I Learned

- How metrics are exposed, scraped and stored in a monitoring pipeline
- Writing basic PromQL queries for CPU, memory, disk and network
- Managing services and troubleshooting on Linux
- Designing a clear dashboard for quick health checks

## 📫 Contact

<a href="https://rafandxb-portfolio.netlify.app/"><img src="https://img.shields.io/badge/Portfolio-5CD6F0?style=for-the-badge&logo=netlify&logoColor=070D1A&labelColor=070D1A" /></a>
<a href="https://www.linkedin.com/in/rafan-rahuf-ab450636b"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=070D1A" /></a>
<a href="mailto:rafanrahuf@gmail.com"><img src="https://img.shields.io/badge/Email-8F86FF?style=for-the-badge&logo=gmail&logoColor=070D1A&labelColor=070D1A" /></a>
