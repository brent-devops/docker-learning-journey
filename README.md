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
**Started:** November 16, 2025

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
