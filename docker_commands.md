
# Docker Commands with Explanations

## 1. `docker run`
Used to run a new container.

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

- `-d`: Run the container in the background (detached mode).
- `-p`: Map container ports with local system ports.
- `--name`: Assign a name to the container.

Example:
```bash
docker run -d -p 8080:80 --name mycontainer nginx
```
This command runs a container from the nginx image, mapping port 8080 on the local system to port 80 inside the container.

## 2. `docker ps`
Display all currently running containers.

```bash
docker ps
```

To display all containers, including stopped ones:
```bash
docker ps -a
```

## 3. `docker stop`
Stop a running container.

```bash
docker stop [CONTAINER_ID/CONTAINER_NAME]
```

Example:
```bash
docker stop mycontainer
```

## 4. `docker start`
Start a stopped container.

```bash
docker start [CONTAINER_ID/CONTAINER_NAME]
```

Example:
```bash
docker start mycontainer
```

## 5. `docker rm`
Remove a container (after stopping it).

```bash
docker rm [CONTAINER_ID/CONTAINER_NAME]
```

To remove multiple containers at once:
```bash
docker rm $(docker ps -a -q)
```

## 6. `docker rmi`
Remove a Docker image.

```bash
docker rmi [IMAGE_ID/IMAGE_NAME]
```

Example:
```bash
docker rmi nginx
```

## 7. `docker exec`
Run a command inside a running container.

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

Example:
```bash
docker exec -it mycontainer /bin/bash
```
This opens a terminal session inside the "mycontainer" container.

## 8. `docker build`
Build a Docker image from a `Dockerfile`.

```bash
docker build [OPTIONS] PATH | URL
```

Example:
```bash
docker build -t myimage .
```
This builds a new image based on the `Dockerfile` in the current directory.

## 9. `docker images`
List all images stored locally.

```bash
docker images
```

## 10. `docker-compose`
Used to run multiple containers using a `docker-compose.yml` file, which defines multiple services.

To run all services defined in the `docker-compose.yml` file:
```bash
docker-compose up
```

To run services in the background:
```bash
docker-compose up -d
```

## 11. `docker logs`
View logs of a container.

```bash
docker logs [CONTAINER_ID/CONTAINER_NAME]
```

Example:
```bash
docker logs mycontainer
```

## 12. `docker pull`
Pull an image from Docker Hub or another registry.

```bash
docker pull [IMAGE_NAME]
```

Example:
```bash
docker pull nginx
```

## 13. `docker network`
Manage Docker networks, such as creating, viewing, or removing a network.

- Create a network:
  ```bash
  docker network create [NETWORK_NAME]
  ```

- List available networks:
  ```bash
  docker network ls
  ```

- Connect a container to a network:
  ```bash
  docker network connect [NETWORK_NAME] [CONTAINER_NAME]
  ```
