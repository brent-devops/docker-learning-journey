# Production Monitoring Stack

Complete observability platform for Docker infrastructure.

## Architecture
```
┌─────────────┐      ┌────────────────┐      ┌──────────────┐
│   Grafana   │─────→│  Prometheus    │─────→│  Exporters   │
│ Dashboards  │      │  Time-Series   │      │              │
│  Port 3000  │      │    Database    │      │ node:9100    │
└─────────────┘      │   Port 9090    │      │ cadvisor:8080│
                     └────────────────┘      └──────────────┘
```

## Components

- **Prometheus (port 9090):** Metrics collection and time-series storage
- **Grafana (port 3000):** Visualization dashboards  
- **Node Exporter (port 9100):** Host system metrics (CPU, RAM, disk, network)
- **cAdvisor (port 8081):** Docker container metrics

## Quick Start
```bash
docker-compose up -d
docker-compose ps
```

## Access Points

- **Prometheus:** http://[VM-IP]:9090
- **Grafana:** http://[VM-IP]:3000
  - Username: `admin`
  - Password: `devops123`
- **cAdvisor:** http://[VM-IP]:8081

## Dashboards

### 1. Node Exporter Full (ID: 1860)
Pre-built dashboard showing complete host system metrics:
- CPU usage (overall and per-core)
- Memory utilization and caching
- Disk space and I/O operations  
- Network traffic and packet rates
- System load and uptime

### 2. Docker Container Monitoring (Custom)
Custom-built dashboard tracking all running containers:
- **Running Containers:** Total count stat
- **Container Memory:** Real-time memory usage per container
- **Container CPU:** CPU utilization percentage per container
- **Container Disk I/O:** Read/write operations per container

## What This Monitors

**Host System:**
- 2-core CPU utilization
- 8 GB RAM usage patterns
- 28 GB root filesystem
- Network interfaces (eth0, docker0)
- System uptime (2.3 weeks)

**Docker Containers (7 running):**
- grafana (visualization)
- prometheus (metrics collection)
- cadvisor (container monitoring)
- node-exporter (host monitoring)
- three-tier-app_web_1 (nginx)
- three-tier-app_db_1 (postgres)
- three-tier-app_api_1 (python)

## Metrics Collected

**Every 15 seconds, Prometheus scrapes:**
- 500+ host system metrics
- 200+ per-container metrics
- Total: ~1,900 metrics every 15 seconds
- Historical data retention: 15 days

## Production Features

✅ **Automatic restarts** - All containers restart on failure
✅ **Persistent storage** - Prometheus data survives restarts  
✅ **Service dependencies** - Correct startup order
✅ **Multi-network architecture** - Isolated communication
✅ **Real-time monitoring** - 15-second refresh rate
✅ **Historical analysis** - 2+ weeks of data retained

## Use Cases

**Performance monitoring:**
- Identify resource-hungry containers
- Track memory leaks over time
- Detect CPU spikes

**Capacity planning:**
- Determine when to scale up
- Identify underutilized resources
- Forecast growth trends

**Troubleshooting:**
- Correlate container issues with host metrics
- Identify cascading failures
- Debug performance degradation

## Technical Details

**Prometheus scrape configuration:**
- Job: prometheus (self-monitoring)
- Job: node-exporter (host metrics)
- Job: cadvisor (container metrics)
- Scrape interval: 15s
- Retention: 15d

**Resource usage:**
- Prometheus: ~150 MB RAM
- Grafana: ~130 MB RAM
- Node Exporter: ~15 MB RAM
- cAdvisor: ~50 MB RAM
- Total overhead: ~345 MB

## Real-World Comparison

This is the same monitoring stack used by:
- Netflix (monitoring 100,000+ containers)
- Uber (real-time infrastructure visibility)
- DigitalOcean (customer infrastructure monitoring)
- GitLab (CI/CD pipeline monitoring)

**Scaled down to home lab, same principles.**

## Status

**Deployed:** November 30, 2025  
**Current uptime:** 2.3 weeks continuous operation  
**Data collected:** 2+ weeks of historical metrics  
**Containers monitored:** 7  
**Metrics tracked:** ~1,900 per scrape  
**Total data points:** 10+ million

---

**Built as part of DevOps learning journey.**  
**Portfolio:** https://github.com/brent-devops/docker-learning-journey



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
