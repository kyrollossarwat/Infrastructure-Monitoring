# Infrastructure Monitoring Suite (AWS EC2 & Telegram Alerts)

A robust monitoring stack built with **Prometheus**, **Node Exporter**, **Alertmanager**, and **Grafana**. This project provides real-time visibility into system metrics across **AWS EC2 instances** with instant notifications delivered via **Telegram**.

## 🚀 Overview
This project monitors hardware and OS-level metrics (CPU, Memory, Disk, Network) across a distributed environment. It is designed to proactively notify administrators the moment an instance becomes unreachable.

### Core Components:
*   **Prometheus**: The core time-series database that scrapes metrics from remote targets.
*   **Node Exporter**: Installed on **2x AWS EC2 instances** to expose host-level metrics.
*   **Alertmanager**: Manages alerts and handles the integration with the **Telegram Bot API**.
*   **Grafana**: The visualization layer for real-time analysis of the EC2 fleet.
*   **Docker Compose**: Orchestrates the monitoring hub in a single, manageable stack.

## 🛠 Features
*   **Multi-Node Monitoring**: Configured to scrape metrics from multiple remote EC2 instances.
*   **Instant Telegram Alerts**: Real-time notifications sent to a **Telegram Bot** if an instance goes down (`up == 0`) or exceeds performance thresholds.
*   **Data Persistence**: Metrics and dashboards are stored via **outside container directory mounting**, ensuring data survives container restarts.
*   **Automated Alert Routing**: Uses Alertmanager to format and deliver critical alerts to your mobile device.


<img width="1918" height="1041" alt="1" src="https://github.com/user-attachments/assets/164317f4-10d5-40b2-bbd2-a69a62275d7d" />
<img width="1920" height="1037" alt="2" src="https://github.com/user-attachments/assets/8e51fb2f-5b0d-4df6-b639-feacb169067d" />
<img width="1920" height="1035" alt="3" src="https://github.com/user-attachments/assets/8c6873b1-9443-4a39-a418-fad9d83cbe1f" />
<img width="1916" height="1037" alt="11" src="https://github.com/user-attachments/assets/e80869ec-bf16-493c-94fa-90710fcc8266" />
<img width="1920" height="1036" alt="21" src="https://github.com/user-attachments/assets/4dde2d90-c516-4f11-a23d-d3522cfc8a56" />
<img width="1920" height="1037" alt="22" src="https://github.com/user-attachments/assets/a4e0f3a1-932a-4a7e-9b98-da9216c4ed0c" />
<img width="1920" height="1032" alt="31" src="https://github.com/user-attachments/assets/4f527e66-3751-470b-93e6-9e3b97a40d68" />
<img width="845" height="951" alt="4" src="https://github.com/user-attachments/assets/a0026f74-c201-492b-917c-5c72f9501a8b" />

## 📂 Project Structure
```text
.
├── docker-compose.yml       # Orchestrates the monitoring hub
├── prometheus/
│   ├── prometheus.yml       # Scrape configs for EC2 IPs
│   └── alert_rules.yml      # Alert logic (e.g., InstanceDown)
├── alertmanager/
│   └── config.yml           # Telegram Bot Token & Chat ID config
└── grafana_data/            # Persistent storage (Mounted Volume)


