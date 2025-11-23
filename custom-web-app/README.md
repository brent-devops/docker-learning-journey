# Custom Web Application

My first custom Docker image built from scratch.

## What This Is

A custom nginx-based web server with my own HTML content, packaged as a Docker image.

## How to Build
```bash
docker build -t brent/custom-web:v1 .
```

## How to Run
```bash
docker run -d -p 8081:80 --name my-custom-web brent/custom-web:v1
```

## What I Learned

- Creating Dockerfile from scratch
- Using base images (nginx:alpine)
- COPY instruction to add content
- Building custom images
- Running custom containers

## Day 3 - November 23, 2025
