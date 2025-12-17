# Docker Learning Journey

Transitioning from Windows System Administrator to DevOps Engineer.

## What I've Built

### ✅ Production Monitoring Stack
Complete observability platform with Prometheus, Grafana, Node Exporter, and cAdvisor.
- Real-time CPU, memory, network, disk metrics
- Docker container monitoring
- 2+ weeks continuous operation
- [View Project](./monitoring-stack/)

### ✅ Three-Tier Application
Multi-container web application with Docker Compose.
- Nginx web server
- Python API
- PostgreSQL database with persistent storage
- [View Project](./three-tier-app/)

### ✅ Custom Docker Images
Built from scratch using Dockerfiles.
- [View Project](./custom-web-app/)

### ✅ Docker Networking Lab
Demonstrations of network isolation and security.
- [View Project](./docker-networking-lab/)

## Progress

**Started:** November 16, 2025  
**Status:** Active  
**Time Invested:** ~25 hours  
**Commits:** 10+  

**Next:** Kubernetes fundamentals

## Skills Acquired

- Docker containerization and orchestration
- Docker Compose multi-container applications
- Prometheus metrics collection and querying
- Grafana dashboard creation and visualization
- Infrastructure as Code principles
- Production monitoring patterns
- Network isolation for security
- Data persistence with volumes

Building in public. Every commit documented.



# Docker Learning Journey

My hands-on learning path from Windows System Administrator to DevOps Engineer.

## Background
- System Administrator at American Pain Consortium Management
- Managing 300+ users with Active Directory, Azure AD, Intune
- PowerShell automation background
- Expanding into containerization and cloud-native infrastructure

## Goals
- Master Docker fundamentals (containers, images, networking, volumes)
- Build production-ready containerized applications
- Deploy to Kubernetes
- Land DevOps Engineer role by May 2026

## Learning Timeline

### Week 1: Docker Fundamentals (Nov 16-22, 2025)
**Started:** November 17, 2025

**Day 1 Achievements:**
- ✅ Set up Ubuntu VM on Proxmox home lab
- ✅ Installed Docker successfully
- ✅ Ran first container (hello-world)
- ✅ Deployed nginx web server on port 8080
- ✅ Created GitHub account and first repository

**First Commands:**
```bash
docker run hello-world
docker run -d -p 8080:80 --name my-first-web nginx:alpine
docker ps
```

**What I learned:**
- Containers are lightweight, isolated application environments
- Containers share the host OS kernel (unlike VMs)
- Port mapping allows external access to containerized services
- Docker pulls images from Docker Hub automatically

### Day 1 Evening - Three-Tier Application Deployment

**Project:** Multi-container application using Docker Compose

**Architecture:**
```
Web Tier (Nginx:8080) → API Tier (Python:8000) → Database Tier (PostgreSQL:5432)
```

**Technical Implementation:**
- **Frontend Network:** Web ↔ API communication
- **Backend Network:** API ↔ Database communication
- **Docker Volumes:** Database data persists across container restarts
- **Service Dependencies:** Proper startup order with depends_on
- **Network Isolation:** Database not exposed to frontend (security)

**Files Created:**
- `docker-compose.yml` - Orchestration configuration
- `html/index.html` - Web frontend
- `api/app.py` - API server placeholder

**Commands Used:**
```bash
docker-compose up -d      # Start all services
docker-compose ps         # Check status
docker-compose logs       # View logs
docker-compose down       # Stop and remove containers
```

**Key Learnings:**
- Docker Compose orchestrates multiple containers from single YAML file
- Networks provide security through isolation (frontend/backend separation)
- Volumes enable stateful applications (database survives restarts)
- Infrastructure as Code: entire stack defined in one file
- Can destroy and rebuild in 5 seconds with identical results

**Real-world Impact:**
This architecture pattern is used by Netflix, Uber, Airbnb for microservices. Learning to build and manage distributed systems at scale.

**Project Directory:** `/three-tier-app/`

**Next Steps:**
- Docker networking deep dive
- Multi-container applications with Docker Compose
- Building custom Docker images with Dockerfiles
- Container data persistence with volumes

---

## Resources I'm Using
- Docker Official Documentation
- "Docker Deep Dive" by Nigel Poulton
- Proxmox home lab for hands-on practice
- GitHub for version control and portfolio building

## Projects

Coming soon: Three-tier web application, monitoring stack, CI/CD pipeline

---

**Building in public. Follow my progress as I transition from traditional infrastructure to modern DevOps practices.**
