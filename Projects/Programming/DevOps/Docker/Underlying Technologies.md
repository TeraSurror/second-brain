### Linux Containers (LXC)
- Server as a foundation for Docker
- Lightweight virtualization solution that allows multiple isolated Linux systems to run on a single host without the need for a full-fledged hypervisor
- isolates applications and their dependencies in a secure and optimized manner

### Control Groups (cgroups)
- allocated and manages resources like CPU, memory and I/O to a set of processes
- Docker uses cgroups to limit resources used by containers

### Union File Systems (UnionFS)
- allows the overlaying of multiple file systems in a single, unified view
- Docker uses it to create a layered approach for images and containers, enabling better sharing of common files and faster container creation

### Namespaces
- Provides process isolation
- allows Docker to create isolated workspaces called containers
- Ensures that processes within a container cannot interfere with processes outside the container or on the host system
- Ex: PID, NET, MNT, and USER 
