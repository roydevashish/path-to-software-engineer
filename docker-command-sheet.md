# Docker Command Sheet

A quick reference for commonly used Docker commands.

Designed for everyday development, it shows how to build, run, manage, and push Docker images. Fully generalized with placeholders for paths, image names, container names, and ports. Minimal, non-redundant, and easy to follow for beginners and intermediate users alike.

---

## Basic Docker Commands

```bash
# Check installed Docker version
docker version

# Pull an image from Docker Hub
docker pull <image_name>

# Build an image from a Dockerfile (path = directory containing Dockerfile)
docker build -t <image_name> <path_to_dockerfile>

# Run a container interactively
docker run -it <image_name>

# Run a container with port mapping (host → container)
docker run -p <host_port>:<container_port> <image_name>

# Run a container with a custom name
docker run -it --name <container_name> <image_name>

# List running containers
docker container ls

# List all containers (including stopped ones)
docker container ls -a

# Stop a container
docker stop <container_id>

# Remove a container
docker container rm <container_id>

# List all images
docker image ls

# Remove an image
docker image rm <image_id>
```

---

## Docker Volumes

```bash
# Create a named volume
docker volume create <volume_name>

# List all volumes
docker volume ls

# Run a container with a mounted host directory
docker run -it -v <host_path>:<container_path> <image_name>

# Run a container with a named volume
docker run -it -v <volume_name>:<container_path> <image_name> bash
```

---

## Docker Networking

```bash
# List all networks
docker network ls

# Inspect the default bridge network
docker inspect bridge

# Create a new network
docker network create <network_name>

# Run a container inside a specific network
docker run -it --network <network_name> --name <container_name> <image_name>

# Connect an existing container to a network
docker network connect <network_name> <container_name>

# Execute a command inside a running container
docker exec -it <container_name> bash

# Run a container with port mapping
docker run -it -p <host_port>:<container_port> <image_name>
```

---

## Working with Docker Hub

```bash
# Build an image and tag it for Docker Hub
docker build -t <dockerhub_username>/<repo_name> <path_to_dockerfile>

# Push image to Docker Hub
docker push <dockerhub_username>/<repo_name>

# Pull image from Docker Hub
docker pull <dockerhub_username>/<repo_name>

# Run container from Docker Hub image
docker run -it <dockerhub_username>/<repo_name>
```

---

This cheatsheet provides a minimal, non-redundant, and fully generalized set of Docker commands for everyday development.

# References
- [Docker Tutorial For Beginners in Hindi by Piyush Garg](https://www.youtube.com/watch?v=zCsbp_iBTq8)
- [Docker Networking | Networking Tutorial in Hindi by Piyush Garg](https://www.youtube.com/watch?v=6t2NhkRsmuA)
- [What is Docker Volume | Docker Volumes Explained by Piyush Garg](https://www.youtube.com/watch?v=VbuNIZIog2w)
- [Docker In One Shot - Part 1 by Piyush Garg](https://www.youtube.com/watch?v=31k6AtW-b3Y&t=1506s)
- [Docker For Open Source Contributors - Part 2 by Piyush Garg](https://www.youtube.com/watch?v=xPT8mXa-sJg)
