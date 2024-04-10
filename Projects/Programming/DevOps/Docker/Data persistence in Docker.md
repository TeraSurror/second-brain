**Ephemeral FS** - The data stored in docker containers is temporary and only exists as long the container exists. This temporary storage is called "ephemeral container file system"

### **Volume mounts**
They are a way to map a folder or a file on the host system to a folder or a file inside a container.
- Create a mount: `docker volume create my-volume`
- Mount a volume to a container: `docker run -d -v my-volume:/data your-image`

### Docker Volumes
- Preferred way of storing data generated and utilized by a docker container
- Volume is a directory on the host machine Docker uses to store files and directories that can outlive the container's lifecycle.
- Can be shared among containers
- create volume: `docker volume create volume_name`
- use volume: `docker run --volume volume_name:/container/path image_name`

### Bind Mounts
- Bind mounts allow you to map any directory on the host machine to a directory within the container.
- create a bind mount: `docker run --mount type=bind,src=/host/path,dst=/container/path image_name`
- they have limited functionality compared to volumes

### Docker tmpfs mounts
- Docker tmpfs mounts allow you to create a temporary file storage directly in the container's memory
- data stored is fast and secure, but is lost once the container is terminated
- command to use mount: `docker rn --tmpfs /container/path image_name`
