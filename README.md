# 🚀 Multi-VM Monitoring with Prometheus & Grafana

A multi-VM infrastructure monitoring system built using **AWS EC2, Prometheus, Grafana, Node Exporter, Docker, and Linux**.

## 🏗️ Architecture

```text
           AWS EC2
              │
      ┌───────┴───────┐
      │               │
     VM2             VM3
  Node Exporter   Node Exporter
     :9100           :9100
      │               │
      └───────┬───────┘
              │
              ▼
             VM1
     ┌─────────────────┐
     │   Prometheus    │
     │      :9090      │
     │                 │
     │     Grafana     │
     │      :3000      │
     └─────────────────
🛠️ Technologies
AWS EC2
Ubuntu Linux
Docker & Docker Compose
Prometheus
Grafana
Node Exporter
Git & GitHub
📁 Project Structure
monitoring/
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml.example
├── .gitignore
└── README.md

The real prometheus.yml containing private EC2 IP addresses is excluded from GitHub.

⚙️ How It Works

Node Exporter runs on VM2 and VM3 and exposes Linux system metrics on port 9100.

Prometheus runs on VM1 and collects these metrics.

Grafana connects to Prometheus and displays the metrics through dashboards.

Node Exporter → Prometheus → Grafana
🚀 Run the Monitoring Stack
docker compose up -d

Check containers:

docker ps

Stop the stack:

docker compose down
🔍 Access

Prometheus:

http://SERVER_IP:9090

Grafana:

http://SERVER_IP:3000

Check Prometheus targets:

Status → Targets

VM2 and VM3 should show UP.

🔐 Security

Sensitive files are excluded using .gitignore:

.env
.env.*
*.pem
*.key
prometheus/prometheus.yml

Private EC2 IP addresses and credentials are not committed to the repository.

🎯 Skills Demonstrated
AWS EC2 infrastructure
Linux administration
Docker & Docker Compose
Prometheus monitoring
Grafana visualization
Node Exporter
Multi-VM monitoring
Git/GitHub
Secure configuration management
👨‍💻 Author

Alan Jose

B.Tech Computer Science & Engineering Graduate┘
