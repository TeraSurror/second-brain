### What are containers
Containers are light weight, portable, and isolated software environments that allow developers to run and package applications with their dependencies, consistently across different platforms.

### How do they work?
- They share the host's OS kernel and leverage lightweight virtualization techniques to create isolated processes.
- Benefits:
	- Efficiency: less overhead and can share common libs and executables.
	- Portability: They encapsulate applications and their dependencies, so they can moved across environments and platforms much faster than VMs
	- Fast startup: containers do not need to boot a full OS, so fast startup
	- Consistency: containers provide a consistent env (same across all systems). No "it works on my machine" problem.
### Docker
- It is a platform that simplifies the process of creating, deploying and managing platforms.
- It provides tools to manage containerized applications
- application code can be converted to an image, which can then be distributed and run on any env that supports Docker.

Notes:
- Container images become containers at runtime

### Bare Metal vs VM vs Containers
#### Bare Metal
Bare metal is a term used to describe a computer that is running directly on the hardware without any virtualization. This is the most performant way to run an application, but it is also the least flexible. You can only run one application per server, and you cannot easily move the application to another server.
#### Virtual Machines
Virtual machines (VMs) are a way to run multiple applications on a single server. Each VM runs on top of a hypervisor, which is a piece of software that emulates the hardware of a computer. The hypervisor allows you to run multiple operating systems on a single server, and it also provides isolation between applications running on different VMs.

#### Containers
Containers are a way to run multiple applications on a single server without the overhead of a hypervisor. Each container runs on top of a container engine, which is a piece of software that emulates the operating system of a computer. The container engine allows you to run multiple applications on a single server, and it also provides isolation between applications running on different containers.

Further reading:
1. https://www.docker.com/resources/what-container/
2. https://explore.skillbuilder.aws/learn/course/106/introduction-to-containers