# 🐳 04. Docker

This guide installs Docker for local development and configures it for daily use.

**⏱️ Estimated Time:** 10–15 minutes

---

## Step 1. Install Docker

Install Docker from the official repositories.

```bash
sudo pacman -S docker
```

---

## Step 2. Enable Docker

Enable Docker to start automatically at boot.

```bash
sudo systemctl enable docker.service
```

Start the Docker service.

```bash
sudo systemctl start docker.service
```

---

## Step 3. Configure Docker

Create the Docker group if it does not already exist.

```bash
sudo groupadd docker
```

> 💡 If the group already exists, you can safely ignore the warning.

Add your user to the Docker group.

```bash
sudo usermod -aG docker $USER
```

Apply the new group membership.

```bash
newgrp docker
```

Alternatively, log out and log back in.

---

## Step 4. Verify Installation

Verify the Docker installation.

```bash
docker --version
docker compose version
```

Run the official test container.

```bash
docker run hello-world
```

---

## Notes

> 💡 Docker Compose is included with modern versions of Docker. There is no need to install the old `docker-compose` package.

> 💡 Adding your user to the `docker` group allows Docker commands to run without `sudo`.

> 💡 I use Docker for PostgreSQL, Redis, Nginx, and containerized development environments.

---

## Useful Commands

### Service Management

| Purpose | Command |
| ------- | ------- |
| Start Docker | `sudo systemctl start docker` |
| Stop Docker | `sudo systemctl stop docker` |
| Restart Docker | `sudo systemctl restart docker` |
| Check service status | `systemctl status docker` |
| Enable Docker on boot | `sudo systemctl enable docker` |
| Disable Docker on boot | `sudo systemctl disable docker` |

Example:

```bash
sudo systemctl restart docker
systemctl status docker
```

---

### Image Management

| Purpose | Command |
| ------- | ------- |
| List images | `docker images` |
| Search Docker Hub | `docker search image_name` |
| Download an image | `docker pull image_name` |
| Remove an image | `docker rmi image_name` |

Example:

```bash
docker search postgres

docker pull postgres:17

docker images
```

---

### Container Management

| Purpose | Command |
| ------- | ------- |
| List running containers | `docker ps` |
| List all containers | `docker ps -a` |
| Create and run a container | `docker run image_name` |
| Stop a container | `docker stop container_name` |
| Start a container | `docker start container_name` |
| Restart a container | `docker restart container_name` |
| Remove a container | `docker rm container_name` |
| View container logs | `docker logs container_name` |
| Open a shell inside a container | `docker exec -it container_name bash` |

Example:

```bash
docker run hello-world

docker ps

docker logs my-container
```

---

### Docker Compose

| Purpose | Command |
| ------- | ------- |
| Start services | `docker compose up` |
| Start services in background | `docker compose up -d` |
| Stop services | `docker compose down` |
| Restart services | `docker compose restart` |
| View logs | `docker compose logs` |
| List running services | `docker compose ps` |

Example:

```bash
docker compose up -d

docker compose ps

docker compose down
```

---

### Cleanup

| Purpose | Command |
| ------- | ------- |
| Remove stopped containers | `docker container prune` |
| Remove unused images | `docker image prune` |
| Remove unused volumes | `docker volume prune` |
| Remove unused networks | `docker network prune` |
| Remove all unused resources | `docker system prune` |

Example:

```bash
docker system prune -a
```

---

## Troubleshooting

### ❌ Cannot connect to the Docker daemon

Verify the Docker service is running.

```bash
sudo systemctl start docker
```

---

### ❌ Permission denied while running Docker

Verify your user belongs to the Docker group.

```bash
groups
```

If necessary, add your user again.

```bash
sudo usermod -aG docker $USER
```

Then log out and log back in.

---

### ❌ Docker service failed

Check the service status.

```bash
systemctl status docker
```

View Docker logs.

```bash
journalctl -u docker
```

---

## Next

➡️ **05-python.md**