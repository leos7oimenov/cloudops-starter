# CloudOps Starter

A beginner DevOps project that demonstrates how to build and run a containerised Python Flask web application on an Ubuntu Server VM using Docker, Docker Compose, Nginx, and PostgreSQL.

## Project Overview

This project runs a simple Flask web application inside a Docker-based multi-container stack. The app is deployed on an Ubuntu Server virtual machine created with VMware Workstation Pro.

The project is being developed in stages to practise core DevOps skills including Linux, SSH, Docker, Docker Compose, reverse proxying, container networking, databases, persistent volumes, health checks, Git, and GitHub.

## Project Versions

### v1 - Manual Docker Deployment

In version 1, the app was built and run manually using Docker commands:

```bash
docker build -t cloudops-starter .
docker run -d -p 5000:5000 --name cloudops-app cloudops-starter
```

This demonstrated basic Docker image creation, container deployment, port mapping, and container testing.

### v2 - Docker Compose Deployment

In version 2, Docker Compose was added so the app can be defined and managed as a service using a `docker-compose.yml` file.

The app can be started with:

```bash
docker compose up -d
```

and stopped with:

```bash
docker compose down
```

This makes the project easier to run, repeat, and expand with more services later.

### v3 - Nginx Reverse Proxy

In version 3, an Nginx container was added as a reverse proxy.

Instead of accessing the Flask app directly on port `5000`, traffic flows through Nginx on port `80`.

```text
User / curl / browser
        ↓
Nginx container on port 80
        ↓
Flask app container on internal port 5000
```

This creates a more realistic multi-container deployment pattern, similar to how applications are commonly exposed in production environments.

### v4 - PostgreSQL Database Integration

In version 4, a PostgreSQL database container was added to make the application stateful.

The Flask app now connects to PostgreSQL using environment variables defined in `docker-compose.yml`. It can create and retrieve simple task records through API endpoints.

The full request flow is now:

```text
User / curl / browser
        ↓
Nginx reverse proxy
        ↓
Flask application container
        ↓
PostgreSQL database container
```

This stage demonstrates multi-container application architecture, container-to-container communication, database configuration, persistent Docker volumes, and basic API/database integration.

## Tech Stack

- Ubuntu Server
- VMware Workstation Pro
- Docker
- Docker Compose
- Nginx
- PostgreSQL
- Python
- Flask
- Git
- GitHub
- PowerShell SSH

## Features

- Flask web application
- Dockerfile for containerisation
- Docker Compose service definition
- Nginx reverse proxy
- PostgreSQL database container
- Multi-container deployment
- Internal Docker networking
- Persistent Docker volume for database data
- Environment-based database configuration
- Health check endpoint with database connectivity check
- API endpoint to create tasks
- API endpoint to retrieve tasks
- GitHub repository with project documentation

## Project Structure

```text
cloudops-starter/
├── app.py
├── Dockerfile
├── docker-compose.yml
├── README.md
├── requirements.txt
└── nginx/
    └── nginx.conf
```

## Endpoints

When running through Nginx:

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Returns a welcome message |
| GET | `/health` | Checks app and database connectivity |
| GET | `/tasks` | Returns saved tasks from PostgreSQL |
| POST | `/tasks` | Creates a new task in PostgreSQL |

## Run with Docker Compose

Start the full setup:

```bash
docker compose up -d --build
```

Check running services:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs
```

Stop the setup:

```bash
docker compose down
```

## Test the App Through Nginx

```bash
curl http://localhost
```

```bash
curl http://localhost/health
```

Expected health response:

```json
{"database":"connected","status":"ok"}
```

## Create a Task

```bash
curl -X POST http://localhost/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"Learn Docker Compose with PostgreSQL"}'
```

Example response:

```json
{"id":1,"title":"Learn Docker Compose with PostgreSQL"}
```

## View Tasks

```bash
curl http://localhost/tasks
```

Example response:

```json
[
  {"id":1,"title":"Learn Docker Compose with PostgreSQL"}
]
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

View Flask app logs:

```bash
docker logs cloudops-app
```

View Nginx logs:

```bash
docker logs cloudops-nginx
```

View PostgreSQL logs:

```bash
docker logs cloudops-postgres
```

View Docker Compose logs:

```bash
docker compose logs
```

Rebuild after changes:

```bash
docker compose up -d --build
```

Stop and remove Compose containers/network:

```bash
docker compose down
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
- How Docker Compose services communicate using service names
- How to configure Nginx as a reverse proxy
- How to route traffic from port 80 to an internal application container
- How to add PostgreSQL as a database container
- How to use environment variables for database configuration
- How to persist database data using Docker volumes
- How to create and retrieve records through API endpoints
- How to commit and push a DevOps project to GitHub

## Next Improvements

- Add a `.env` file for cleaner environment variable management
- Add GitHub Actions CI pipeline
- Add automated Docker image build
- Add Prometheus and Grafana monitoring
- Add basic security scanning
- Add AWS/Terraform deployment later
