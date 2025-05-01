- an open-source project that automates the deployment of software applications inside **containers** by providing an additional layer of abstraction and automation of **OS-level virtualization** on Linux.
- Docker allows you to create lightweight, self-contained environments that run consistently on any system,
- \_**docker run** is the command used in Docker to create and start containers based on Docker images
-  A **Docker Image** contains everything a container needs to run, including the application code, libraries, dependencies, and the operating system it needs. Images are blueprints or templates for **containers**.

- Built from a `Dockerfile`.
- **Docker Engine,** also known as Docker Daemon, is the core component of the Docker platform responsible for running and managing Docker containers.
- The **Docker network** is a virtual network created by Docker to enable communication between [Docker containers](https://www.geeksforgeeks.org/containerization-using-docker/).
- Managing multiple containers can get complex! **Docker Compose** simplifies this process. In this section we have listed down all the details about the Docker Compose like intro and Compose tools.
- A **Docker environment** is your working setup that includes: Docker engine + CLI + (optional) Docker Desktop + configuration tools like Compose, images, containers, volumes, and networks.
- **Volumes store data outside of containers.** Data inside containers is **temporary** (lost if container stops). Volumes are used to **persist** data — for example, databases, uploads. You can also share data between your computer and the container.

#### Common Dockerfile Instructions

| Instruction | Description                                                   | Example                    |
| ----------- | ------------------------------------------------------------- | -------------------------- |
| `FROM`      | Specifies the base image                                      | `FROM node:18`             |
| `WORKDIR`   | Sets the working directory inside the container               | `WORKDIR /app`             |
| `COPY`      | Copies files from your machine to the container               | `COPY . .`                 |
| `RUN`       | Executes a command during image build (e.g. install packages) | `RUN npm install`          |
| `CMD`       | Sets the default command to run when the container starts     | `CMD ["node", "index.js"]` |
| `EXPOSE`    | Documents which port the container listens on (optional)      | `EXPOSE 3000`              |
| `ENV`       | Sets environment variables inside the container               | `ENV NODE_ENV=production`  |
|             |                                                               |                            |


#### SetUp
1. setupDockerfile -it says to docker how to create image and container a set of instructions
2. create .dockerignore
3. create docker image 
```
docker build -t [IMAGE NAME] 
```
4. run conteiner
```
docker run -p 8000:8000 [IMAGE NAME]
```
- **First `8000` (host port)** — The port on **your machine** (e.g., localhost:8000).
- **Second `8000` (container port)** — The port inside the **container** that your app listens on.

### Commands

1. Image & Build Commands

| Command                          | Purpose                                                           |
| -------------------------------- | ----------------------------------------------------------------- |
| `docker build -t <image-name> .` | Build a Docker image from the Dockerfile in the current directory |
| `docker images`                  | List all locally stored images                                    |
| `docker rmi <image-id or name>`  | Remove a Docker image                                             |

2. Container Commands

|Command|Purpose|
|---|---|
|`docker run -p 8000:8000 <image-name>`|Run a container from an image with port mapping|
|`docker run -it <image-name>`|Run a container interactively (e.g., with bash)|
|`docker ps`|Show running containers|
|`docker ps -a`|Show all containers (running and stopped)|
|`docker stop <container-id>`|Stop a running container|
|`docker start <container-id>`|Start a stopped container|
|`docker rm <container-id>`|Remove a container|

3. **Clean-Up Commands**

|Command|Purpose|
|---|---|
|`docker system prune`|Remove all stopped containers, unused networks, and dangling images|
|`docker volume prune`|Remove unused volumes|

4. Volume & File Commands

|Command|Purpose|
|---|---|
|`docker cp <container-id>:<path-inside> <host-path>`|Copy files from container to host|
|`docker cp <host-path> <container-id>:<path-inside>`|Copy files from host to container|
|`docker volume ls`|List all volumes|
|`docker volume rm <volume-name>`|Delete a specific volume|

