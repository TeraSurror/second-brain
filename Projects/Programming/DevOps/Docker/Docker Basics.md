
### Components
- **Dockerfile**: A text file containing instructions (commands) to build a Dokcer image
- Docker Image: 
	- A snapshot of a container, created from a Dockerfile
	- Images can be stored in a registry, like Docker Hub and can be pulled or pushed to the registry
- Docker Container: A running instance of a Docker image


### Docker Commands
- `docker pull <image>` : Download an image from a registry
- `docker build -t <image_name> <path>`: Build an image from a Dockerfile, where path is the directory containing the Dockerfile
- `docker image ls`: List all the images available on your local machine
- `docker image rm <image>`: Remove an image from local machine
- `docker image rm <image>`: Remove an image from local machine
- `docker run -d -p <host_port>:<container_port> --name <container_name> <image>`: Run a container from an image, mapping hosts to container ports
- `docker container ls`: List all running containers
- `docker container stop <container>` : Stop a running container
- `docker container rm <container>`: Remove a stopped container