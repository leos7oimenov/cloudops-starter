# CloudOps Starter

A beginner DevOps project that demonstrates how to build and run a containerised Python Flask web application on an Ubuntu Server VM using Docker.

## Tech Stack

- Ubuntu Server
- VMware Workstation Pro
- Docker
- Python
- Flask
- PowerShell SSH

## Features

- Flask web application
- Dockerfile for containerisation
- Docker image build
- Docker container deployment
- Port mapping from host to container
- Health check endpoint

## Endpoints

- `/` returns a welcome message
- `/health` returns application health status

## Build

```bash
docker build -t cloudops-starter .
```

## Run

```bash
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

## Test

```bash
curl http://localhost:5000
curl http://localhost:5000/health
```

## Useful Commands

```bash
docker ps
docker logs cloudops-app
docker stop cloudops-app
docker start cloudops-app
```

## Next Improvements

- Add Docker Compose
- Add Nginx reverse proxy
- Add PostgreSQL database
- Add GitHub Actions CI pipeline
- Add Prometheus and Grafana monitoring
