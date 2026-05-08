# CloudOps Starter

A beginner DevOps project that demonstrates how to build and run a containerised Python Flask web application on an Ubuntu Server VM using Docker and Docker Compose.

## Project Overview

This project runs a simple Flask web application inside a Docker container. The app is deployed on an Ubuntu Server virtual machine created with VMware Workstation Pro.

The goal of this project is to practise core DevOps skills including Linux, SSH, Docker, Docker Compose, container builds, port mapping, health checks, Git, and GitHub.

## Project Versions

### v1 - Manual Docker Deployment

In version 1, the app was built and run manually using Docker commands:

```bash
docker build -t cloudops-starter .
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

This demonstrated basic Docker image creation, container deployment, and port mapping.

### v2 - Docker Compose Deployment

In version 2, Docker Compose was added so the app can be defined and managed as a service using a `docker-compose.yml` file.

The app can now be started with:

```bash
docker compose up -d
```

and stopped with:

```bash
docker compose down
```

This makes the project easier to run, repeat, and expand with more services later.

## Tech Stack

- Ubuntu Server
- VMware Workstation Pro
- Docker
- Docker Compose
- Python
- Flask
- Git
- GitHub
- PowerShell SSH

## Features

- Flask web application
- Dockerfile for containerisation
- Docker image build
- Docker Compose service definition
- Container deployment
- Port mapping from host to container
- Health check endpoint
- GitHub repository with project documentation

## Project Structure

```text
cloudops-starter/
├── app.py
├── Dockerfile
├── docker-compose.yml
├── README.md
└── requirements.txt
```

## Endpoints

- `/` returns a welcome message
- `/health` returns application health status

## Build Manually with Docker

```bash
docker build -t cloudops-starter .
```

## Run Manually with Docker

```bash
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

## Run with Docker Compose

Start the app:

```bash
docker compose up -d
```

Check the running service:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs
```

Stop the app:

```bash
docker compose down
```

Rebuild after code changes:

```bash
docker compose up -d --build
```

## Test the App

```bash
curl http://localhost:5000
```

```bash
curl http://localhost:5000/health
```

Expected health response:

```json
{"status":"ok"}
```

## Useful Docker Commands

Check running containers:

```bash
docker ps
```

Check all containers:

```bash
docker ps -a
```

View container logs:

```bash
docker logs cloudops-app
```

Stop the container:

```bash
docker stop cloudops-app
```

Start the container:

```bash
docker start cloudops-app
```

Remove the container:

```bash
docker rm cloudops-app
```

## What I Learned

- How to create and use an Ubuntu Server VM
- How to connect to a Linux server using SSH
- How to create a simple Flask web app
- How to write a Dockerfile
- How to build a Docker image
- How to run a Docker container
- How to expose container ports
- How to test a containerised app using curl
- How to define services using Docker Compose
- How to commit and push a DevOps project to GitHub

## Next Improvements

- Add Nginx reverse proxy
- Add PostgreSQL database
- Add GitHub Actions CI pipeline
- Add Prometheus and Grafana monitoring
- Add basic security scanning
E
cat > README.md <<'EOF'
# CloudOps Starter

A beginner DevOps project that demonstrates how to build and run a containerised Python Flask web application on an Ubuntu Server VM using Docker and Docker Compose.

## Project Overview

This project runs a simple Flask web application inside a Docker container. The app is deployed on an Ubuntu Server virtual machine created with VMware Workstation Pro.

The goal of this project is to practise core DevOps skills including Linux, SSH, Docker, Docker Compose, container builds, port mapping, health checks, Git, and GitHub.

## Project Versions

### v1 - Manual Docker Deployment

In version 1, the app was built and run manually using Docker commands:

```bash
docker build -t cloudops-starter .
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

This demonstrated basic Docker image creation, container deployment, and port mapping.

### v2 - Docker Compose Deployment

In version 2, Docker Compose was added so the app can be defined and managed as a service using a `docker-compose.yml` file.

The app can now be started with:

```bash
docker compose up -d
```

and stopped with:

```bash
docker compose down
```

This makes the project easier to run, repeat, and expand with more services later.

## Tech Stack

- Ubuntu Server
- VMware Workstation Pro
- Docker
- Docker Compose
- Python
- Flask
- Git
- GitHub
- PowerShell SSH

## Features

- Flask web application
- Dockerfile for containerisation
- Docker image build
- Docker Compose service definition
- Container deployment
- Port mapping from host to container
- Health check endpoint
- GitHub repository with project documentation

## Project Structure

```text
cloudops-starter/
├── app.py
├── Dockerfile
├── docker-compose.yml
├── README.md
└── requirements.txt
```

## Endpoints

- `/` returns a welcome message
- `/health` returns application health status

## Build Manually with Docker

```bash
docker build -t cloudops-starter .
```

## Run Manually with Docker

```bash
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

## Run with Docker Compose

Start the app:

```bash
docker compose up -d
```

Check the running service:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs
```

Stop the app:

```bash
docker compose down
```

Rebuild after code changes:

```bash
docker compose up -d --build
```

## Test the App

```bash
curl http://localhost:5000
```

```bash
curl http://localhost:5000/health
```

Expected health response:

```json
{"status":"ok"}
```

## Useful Docker Commands

Check running containers:

```bash
docker ps
```

Check all containers:

```bash
docker ps -a
```

View container logs:

```bash
docker logs cloudops-app
```

Stop the container:

```bash
docker stop cloudops-app
```

Start the container:

```bash
docker start cloudops-app
```

Remove the container:

```bash
docker rm cloudops-app
```

## What I Learned

- How to create and use an Ubuntu Server VM
- How to connect to a Linux server using SSH
- How to create a simple Flask web app
- How to write a Dockerfile
- How to build a Docker image
- How to run a Docker container
- How to expose container ports
- How to test a containerised app using curl
- How to define services using Docker Compose
- How to commit and push a DevOps project to GitHub

## Next Improvements

- Add Nginx reverse proxy
- Add PostgreSQL database
- Add GitHub Actions CI pipeline
- Add Prometheus and Grafana monitoring
- Add basic security scanning
