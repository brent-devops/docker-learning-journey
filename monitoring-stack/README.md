# Monitoring Stack

Production-grade monitoring with Prometheus and Grafana.

## What This Is

- **Prometheus:** Metrics collection and storage
- **Grafana:** Visualization and dashboards

## How to Run
```bash
docker-compose up -d
```

## Access

- Prometheus: http://[VM-IP]:9090
- Grafana: http://[VM-IP]:3000
  - Username: admin
  - Password: devops123

## What It Monitors

Currently monitoring Prometheus itself. Will expand to:
- Host metrics (CPU, memory, disk)
- Docker container metrics
- Application metrics

## Architecture
```
Grafana (dashboards) → Prometheus (metrics) → Targets (applications)
```

## Status

- ✅ Prometheus deployed and scraping
- ✅ Grafana deployed and accessible
- 🚧 Adding exporters (Saturday deep work)
- 🚧 Creating custom dashboards
- 🚧 Setting up alerts

Built: November 30, 2025
