![Build Status](https://img.shields.io/github/actions/workflow/status/DanLinX2004X/monitron/docker-compose-test.yml?branch=main)
![License](https://img.shields.io/badge/license-MIT-green)
![Docker](https://img.shields.io/badge/docker-compose-v2.15-blue)
![Prometheus](https://img.shields.io/badge/prometheus-v2.48-orange)
![Grafana](https://img.shields.io/badge/grafana-10.2-purple)
![Alertmanager](https://img.shields.io/badge/alertmanager-active-red)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions)

# 🚀 Monitron

Personal Monitoring Stack for developers and DevOps engineers.

Monitron is a ready-to-use monitoring stack that helps you collect, analyze, and visualize metrics from your applications and infrastructure.  
Perfect for pet projects, home labs, and DevOps practice environments.

---

## ✨ Features

- 📊 Metrics collection — Prometheus for time-series data storage  
- 📈 Visualization — Grafana dashboards ready to use  
- 🚨 Alerting — Alertmanager with Telegram integration  
- 🖥 System monitoring — Node Exporter for host metrics  
- 🌐 Web monitoring — Nginx + Exporter for web server stats  
- 🔄 CI/CD — automatic configuration validation and build tests  

---

## 🛠 Stack Components

| Component | Version | Description |
|------------|----------|-------------|
| Prometheus | 2.48 | Metrics collection & storage |
| Grafana | 10.2 | Visualization & dashboards |
| Alertmanager | — | Alert routing & notifications |
| Node Exporter | — | Host-level metrics |
| Docker Compose | 2.15 | Container orchestration |
| GitHub Actions | — | CI/CD automation |

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/DanLinX2004X/monitron.git
cd monitron

# 2. Create an .env file from the template
cp .env.example .env

# 3. Launch the monitoring stack
docker compose up -d --build

# 4. Check running services
docker compose ps
```

---

## 🔗 Service Access

Service URL Login

Grafana http://localhost:3000 admin / admin
Prometheus http://localhost:9090 —
Alertmanager http://localhost:9093 —
Nginx http://localhost:8080 —

P.S. Login and password are required to log in to Grafana. When you open it for the first time, it will be admin/ admin (login and password match), after that Grafana will ask you to change the password.

---

## 📦 Stop Services

```
docker compose down
```

---

⚙️ Alertmanager & Telegram Integration

The .env.example file contains variables for Telegram notification setup:

```text
TELEGRAM_BOT_TOKEN=123456789:ABCDEF123456789
TELEGRAM_CHAT_ID=123456789
```

Once filled in, Alertmanager will automatically send alerts to your Telegram chat.


---

## 📊 Grafana Dashboards

System Overview — CPU, memory, disk, network

Nginx Analytics — requests, connections, errors



---

## 🏗 Project Structure

```text
monitron/
├── 📁 prometheus/
│   ├── config/
│   │   ├── prometheus.yml       # Main configuration
│   │   └── alert.rules.yml      # Alert rules
│   └── data/                    # Time series data
├── 📁 grafana/
│   └── provisioning/            # Auto setup files
├── 📁 nginx/
│   ├── html/
│   │   └── index.html           # Demo page
│   └── nginx.conf               # Web server config
├── 📁 screenshots/              # Screenshots for documentation
│   ├── system_dashboard.png
│   └── nginx_monitoring.png
├── 🐳 docker-compose.yml        # Main Docker Compose file
├── 📜 .env.example              # Environment variables
├── 📘 README.md                 # Documentation (RU)
└── 📘 README.en.md              # Documentation (EN)
```

---

## 🔄 CI/CD Pipeline

Automated workflow using GitHub Actions:

✅ Docker Compose syntax validation

✅ Prometheus config validation (promtool check config)

✅ Health check of running containers

✅ Build and deploy verification



---

## ⚠️ Local Testing with act

You can run the pipeline locally using:

```bash
act -j validate
```

> ⚠️ Note: act has known limitations (network isolation, health-checks, volume mapping).
For reliable testing — use real GitHub Actions runners.


---

📸 Screenshots

System Dashboard
![[screenshots/system_dashboard.png]]



Nginx Monitoring
![[screenshots/nginx_monitoring.png]]




---

🤝 Contributing

1. Fork the repository


2. Create a feature branch: git checkout -b feature/amazing-feature


3. Commit changes: git commit -m 'Add amazing feature'


4. Push the branch: git push origin feature/amazing-feature


5. Open a Pull Request




---

📄 License

Distributed under the MIT License.


---

👤 Author

DanLinX2004X

