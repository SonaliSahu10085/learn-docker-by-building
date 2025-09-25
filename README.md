# learn-docker-by-building
Beginner-friendly Docker guide with hands-on project examples.

# 🐳 Docker Basics

## Why Docker?
Docker solves the famous problem:  
**"It works on my machine, but not on others."**

- **Docker Container**: Helps us to share our system in a **standardized way** with others.

---

## Containers
- **Portable** – Can run anywhere.
- **Lightweight** – Less overhead, easy to create and destroy.
- **Instance of Docker Images** – Occupies memory when running.

---

## Docker Images
- **Executable files of minimal size** that contain everything needed to run an app.  
- We **share images** across different machines.
- **Analogy**:  
  - **Docker Image → Class**  
  - **Docker Container → Object**

---

## Docker Installation
- Visit 👉 [docker.com](https://www.docker.com) (download Docker Desktop)

---

## Docker Desktop
- Shows all **containers and images** running on our system.

### Verify Installation
```bash
docker       # Prints list of available commands
docker -v    # Prints Docker version
```

## Docker Hub
- Visit 👉 [hub.docker.com](https://www.hub.docker.com)
- It’s like GitHub, but instead of code, it stores Docker images.

## Important Basic Commands
```bash
docker pull IMAGE_NAME         # Pull image from Docker Hub
docker images                  # Show images on local system
docker run IMAGE_NAME          # Build & run new container
docker run -it IMAGE_NAME      # Run container in interactive mode (user input/output)
docker ps -a                   # Show all containers (running + stopped)
docker ps                      # Show only running containers
docker start CONT_NAME/CONT_ID # Start an existing container
docker stop CONT_NAME/CONT_ID  # Stop a running container
```
## Docker Daemon
- Core part of Docker Desktop that does all the important work in the background.


## Container States
- **Running** → Using system resources.  
- **Exited** → Stopped, but still exists on Docker Desktop.


## Docker vs Virtual Machines

### Docker
- Uses host OS kernel.  
- Virtualizes only the **application layer**.  
- Lightweight, less overhead.  

### Virtual Machines
- Has its own kernel.  
- Virtualizes **application layer + OS kernel**.  
- Heavyweight, more overhead.  


## Docker Disadvantage
- Initially, Docker worked only on **Linux-based systems** (most Docker images are Linux-based).  
- On **Windows & macOS**, Docker Desktop provides a **thin Linux VM / hypervisor** in the background.  


## Docker Image vs Container

### Image
- Read-only template.  
- Built in **layers**:  
  - Base layer (Linux), layer 1, layer 2, …, container layer.  
- Only the top container layer allows **read/write**.  

### Container
- Instance of an image.  
- Has its own **virtual file system**.  
- Cannot access host file system directly.  

---

## More Docker Commands
```bash
docker pull IMAGE_NAME:version   # Pull specific version of an image
docker rm CONT_ID/CONT_NAME      # Remove a container
docker rmi IMAGE_ID/IMAGE_NAME   # Remove an image (only if no container uses it)
docker run -d IMAGE_NAME         # Run container in detached mode (background)
```

## Attach vs Detach Mode

### Attach Mode (default)
- Like sitting inside a bus → you see everything live.
- If you exit (`Ctrl+C`), the bus (container) stops.

### Detach Mode (-d)
- Like sending the bus without sitting inside.
- Runs in background, you are free.
- You can later check logs with `docker logs`.
