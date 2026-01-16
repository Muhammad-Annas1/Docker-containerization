# Docker Containerization Project

This repository contains two separate containerized applications demonstrating Docker containerization techniques:

1. **FastAPI Application** - A Python-based REST API using FastAPI
2. **Next.js Application** - A React-based web application using Next.js

## 📁 Project Structure

```
dockerfile-image-container/
├── fastapi-docker/          # FastAPI application
│   ├── Dockerfile           # Docker configuration for FastAPI
│   ├── main.py              # FastAPI application code
│   ├── pyproject.toml       # Python dependencies
│   └── .python-version      # Python version specification
├── nextjs-docker/           # Next.js application
│   ├── Dockerfile           # Docker configuration for Next.js
│   ├── package.json         # Node.js dependencies
│   ├── app/                 # Next.js app directory
│   └── public/              # Static assets
└── screenshots/             # Docker Desktop screenshots
    ├── 1_fastapi_container.png
    ├── 2_fastapi_layers.png
    ├── 3_nextjs_container.png
    └── 4_nextjs_layers.png
```

## 🚀 FastAPI Application

### Overview
A simple FastAPI REST API that returns a JSON response at the root endpoint.

### Technology Stack
- **Python**: 3.12
- **Framework**: FastAPI
- **Package Manager**: uv

### Build & Run

```bash
# Navigate to the FastAPI directory
cd fastapi-docker

# Build the Docker image
docker build -t fastapi-app .

# Run the container
docker run -p 8000:8000 fastapi-app

# Access the application
# Open your browser and navigate to: http://localhost:8000
```

### API Endpoints
- `GET /` - Returns: `{"message": "Hello from FastAPI Docker!"}`

### Dockerfile Details
- **Base Image**: `python:3.12-slim`
- **Working Directory**: `/app`
- **Exposed Port**: `8000`
- **Package Manager**: Uses `uv` for fast dependency installation

## ⚛️ Next.js Application

### Overview
A Next.js web application built with React, demonstrating modern web development practices.

### Technology Stack
- **Node.js**: 22
- **Framework**: Next.js (React)
- **Package Manager**: npm

### Build & Run

```bash
# Navigate to the Next.js directory
cd nextjs-docker

# Build the Docker image
docker build -t nextjs-app .

# Run the container
docker run -p 3000:3000 nextjs-app

# Access the application
# Open your browser and navigate to: http://localhost:3000
```

### Dockerfile Details
- **Base Image**: `node:22-alpine`
- **Working Directory**: `/app`
- **Exposed Port**: `3000`
- **Build Process**: Multi-stage with dependency installation and production build

## 📸 Screenshots

The `screenshots/` directory contains Docker Desktop screenshots showing:
- Running containers for both applications
- Image layer information for optimization analysis

## 🛠️ Prerequisites

Before running these applications, ensure you have:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed
- Docker daemon running
- Sufficient disk space for image builds

## 📝 Usage Instructions

### Running Both Applications Simultaneously

```bash
# Terminal 1 - FastAPI
cd fastapi-docker
docker build -t fastapi-app .
docker run -p 8000:8000 fastapi-app

# Terminal 2 - Next.js
cd nextjs-docker
docker build -t nextjs-app .
docker run -p 3000:3000 nextjs-app
```

### Stopping Containers

```bash
# List running containers
docker ps

# Stop a specific container
docker stop <container_id>

# Remove a container
docker rm <container_id>
```

### Viewing Container Logs

```bash
# View logs for a running container
docker logs <container_id>

# Follow logs in real-time
docker logs -f <container_id>
```

## 🔍 Docker Commands Reference

```bash
# List all images
docker images

# List running containers
docker ps

# List all containers (including stopped)
docker ps -a

# Remove an image
docker rmi <image_name>

# Remove all stopped containers
docker container prune

# Remove all unused images
docker image prune -a
```

## 📦 Docker Best Practices Implemented

1. **Multi-stage builds** - Optimized image sizes
2. **Specific base images** - Using slim/alpine variants
3. **.dockerignore** - Excluded unnecessary files
4. **Layer caching** - Optimized build times by ordering commands efficiently
5. **Port exposure** - Clearly defined exposed ports
6. **Working directories** - Organized file structure within containers

## 🤝 Contributing

This is an educational project demonstrating Docker containerization. Feel free to fork and modify for your learning purposes.

## 📄 License

This project is open source and available for educational purposes.

## 👨‍💻 Author

Muhammad Annas

## 🔗 Repository

[GitHub - Docker Containerization](https://github.com/Muhammad-Annas1/Docker-containerization.git)
