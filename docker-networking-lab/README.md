# Docker Networking Lab

Hands-on experiments with Docker networks.

## Experiment 1: Custom Networks

Created custom network and demonstrated container-to-container communication using DNS.
```bash
docker network create myapp-network
docker run -d --name web --network myapp-network nginx:alpine
docker run -d --name client --network myapp-network alpine sleep 3600
docker exec -it client ping web  # Works! DNS resolves container names
```

**Key learning:** Containers on same network can communicate using container names as hostnames.

## Experiment 2: Network Isolation

Demonstrated network isolation for security.
```bash
docker network create database-network
docker run -d --name database --network database-network postgres:15-alpine
docker exec web ping database  # FAILS - different networks
docker network connect database-network web
docker exec web ping database  # NOW WORKS - web on both networks
```

**Key learning:** Containers on different networks cannot communicate (isolation = security). Can connect containers to multiple networks as needed.

## Real-world application:
- Frontend network: Web servers
- Backend network: APIs
- Database network: Databases only

Web connects to frontend + backend.
API connects to backend + database.
Database only on database network.

This is how Netflix/Uber architect their systems.
