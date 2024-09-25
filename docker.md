**Docker Concepts Revision Guide**

**1. Introduction to Docker**

- What is Docker?
- Importance of containerization.
- Differences between Containers and Virtual Machines.
- Overview of Docker architecture (Docker Engine, Docker Hub, etc.).

---

**2. Docker Installation**

- System requirements for Docker.
- Installation methods for different operating systems (Windows, macOS, Linux).

---

**3. Docker Images**

- What is a Docker image?
- Creating Docker images using `Dockerfile`.
- Commonly used commands:
  - `docker build`: Build an image from a Dockerfile.
    ```bash
    docker build -t image_name:tag .
    ```
  - `docker pull`: Download an image from Docker Hub.
    ```bash
    docker pull image_name:tag
    ```
  - `docker images`: List all Docker images on the local system.
    ```bash
    docker images
    ```
  - `docker rmi`: Remove a Docker image.
    ```bash
    docker rmi image_name:tag
    ```

---

**4. Docker Containers**

- What is a Docker container?
- Creating and managing containers:
  - `docker run`: Create and start a container.
    ```bash
    docker run -d --name container_name image_name:tag
    ```
  - `docker ps`: List running containers.
    ```bash
    docker ps
    ```
  - `docker ps -a`: List all containers (running and stopped).
  - `docker stop`: Stop a running container.
    ```bash
    docker stop container_name
    ```
  - `docker start`: Start a stopped container.
  - `docker exec`: Execute a command in a running container.
    ```bash
    docker exec -it container_name bash
    ```
  - `docker rm`: Remove a container.
    ```bash
    docker rm container_name
    ```

---

**5. Docker Networking**

- Overview of Docker networking options.
- Network types:
  - **Bridge**: Default network, isolated environment.
  - **Host**: Shares the host network stack.
  - **None**: No network.
  - **Overlay**: Enables communication between multiple Docker hosts.
- Common commands:
  - `docker network ls`: List networks.
  - `docker network create`: Create a new network.
    ```bash
    docker network create network_name
    ```
  - `docker network inspect`: Display network details.

---

**6. Docker Volumes**

- What are Docker volumes?
- Why use volumes (persistent data storage)?
- Common commands:
  - `docker volume ls`: List volumes.
  - `docker volume create`: Create a new volume.
    ```bash
    docker volume create volume_name
    ```
  - `docker volume rm`: Remove a volume.
    ```bash
    docker volume rm volume_name
    ```

---

**7. Docker Compose**

- What is Docker Compose?
- Benefits of using Docker Compose for multi-container applications.
- Common commands:
  - `docker-compose up`: Start services defined in `docker-compose.yml`.
  - `docker-compose down`: Stop and remove containers, networks, and volumes.
  - `docker-compose build`: Build or rebuild services.
- Sample `docker-compose.yml` structure:
  ```yaml
  version: "3"
  services:
    web:
      image: nginx
      ports:
        - "80:80"
    db:
      image: mysql
      environment:
        MYSQL_ROOT_PASSWORD: example
  ```

---

**8. Docker Registry**

- What is a Docker registry?
- Docker Hub vs. private registries.
- Common commands:
  - `docker login`: Authenticate to a Docker registry.
  - `docker push`: Upload an image to a registry.
    ```bash
    docker push image_name:tag
    ```
  - `docker pull`: Download an image from a registry.

---

**9. Dockerfile**

- What is a Dockerfile?
- Basic structure of a Dockerfile:
  ```Dockerfile
  FROM base_image
  MAINTAINER your_name
  RUN command
  COPY src dest
  CMD ["executable", "param1", "param2"]
  ```
- Common instructions:
  - `FROM`: Base image to use.
  - `RUN`: Execute commands during image build.
  - `COPY`: Copy files/directories into the image.
  - `CMD`: Specify the default command to run in the container.
  - `ENTRYPOINT`: Configure a container that will run as an executable.

---

**10. Docker Best Practices**

- Keep images small (multi-stage builds).
- Use specific tags (avoid `latest`).
- Clean up unused images and containers.
- Use `.dockerignore` to exclude files from the build context.

---

**11. Monitoring and Logging**

- Tools for monitoring Docker containers (Prometheus, Grafana).
- Docker logging drivers (json-file, syslog, fluentd).
- Viewing logs:
  ```bash
  docker logs container_name
  ```

---

**12. Security Best Practices**

- Use official images when possible.
- Regularly update images and containers.
- Limit container privileges (use `--cap-drop`).
- Implement network segmentation.

---
