# 🐳 Docker Command Cheatsheet

## 1. **Running a Container**
- **Command:**
  ```
  docker run <image-name>:<tag-name>
  ```
- **Description:**
Picks the image and creates a container for it. If the image is not present, Docker tries to download it from the hub.
Example:
    ```cmd
    docker run busybox:latest
    ```

## 2. **Pulling an Image**
- **Command:**
    ```
    docker pull <image-name>:<tag-name>
    ```
- **Description:**
Pull the images from Docker Hub, which acts as a repository for storing images.

## 3. **Listing All Images**
- **Command:**
    ```   
    docker images
    ```
- **Description:**
  Lists all images available on your local system.

## 4. **Starting an Existing Container**
- **Command:**
  ```
  docker start -a -i <container_id/container_name>
  ```
- **Description:**
  Starts the existing container.

## 5. **Listing All Containers**
- **Command:**
  ```
  docker container ls
  ```
  OR
  ``` 
  docker container ls -a
  ```
- **Description:**
  Lists all running containers or all containers including stopped ones.

## 6. **Removing All Containers**
- **Command:**
  ```
  docker container prune
  ```
- **Description:**
  Removes all stopped containers.

## 7. **Running Container in Daemon Mode**
- **Command:**
  ```
  docker run -d <image>
  ```
- **Description:**
  Runs a container in the background (detached mode).

## 8. **Naming a Container**
- **Command:**
  ```
  docker run -d --name <container_name> <image>
  ```
- **Description:**
  Runs a container with a specified name.

## 9. **Port Mapping**
- **Command:**
  ```
  docker run -d --name <container_name> -p <host_port>:<container_port> <image>
  ```
- **Description:**
  Maps the container's port to the host's port. E.g., ```-p 6000:8080``` maps port 8080 of the container to port 6000 on localhost.

## 10. **Building a Dockerfile**
- **Key Commands:**
    ```dockerfile
    FROM: Import a base image for building your own image.
    WORKDIR: Set the working directory inside the container.
    COPY: Copies files from the host to the container.
    RUN: Execute commands in the container, e.g., installing dependencies.
    CMD: Specify the command to run after the container starts.
    ```
## 11. **Building an Image**
- **Command:**
  ```
  docker build --no-cache -t <name> .
  ```
- **Description:**
  Builds an image from a Dockerfile, using ```--no-cache``` to pull the latest versions of the existing images. The ```-t``` flag tags the image.

## 12. **Checking All Containers**
- **Command:**
  ```
  docker ps -a
  ```
- **Description:**
  Lists all containers, both running and stopped.

## 13. **Exposing a Port**
- **Command:**
  ```
  docker run -p <host_port>:<container_port>
  ```
- **Description:**
  Exposes a port on the container to the host.

## 14. **Docker Network**
- **Key Commands:**
    - **View Networks:**
      ```docker network ls```
    - **Remove a Network:**
      ```docker network rm <network_name>```
    - **Inspect a Network:**
      ```docker network inspect <network_name>```
    - **Create a New Network:**
      ```docker network create <network_name>```
    - **Run a Container in a Network:**
      ```docker run --net <network_name> <image_name>```

## 15. **Docker Compose**
- **Key Fields:**
    - **Version:** Specify the Docker version.
    - **Services:** List all containers to be used.
        - **Image:** The name of the image.
        - **Container_name:** The name of the container.
        - **Volumes:** Host directory : Container directory : ro (read-only)
        - **Ports:** Host port : Container port
