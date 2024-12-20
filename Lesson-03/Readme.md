## Hello World in Docker - Intro to Docker Basics

### Now that you have installed Docker and running on your machine, it's time for you to run your first container. Open up the terminal and run the following command:

```
docker run hello-world
```

### Now in your terminal, you can use the docker ps -a command to have a look at all the containers that are currently running or have run in the past:

### Let's assume in the output, a container named `new_container` was run with the container id of `128ec8ceab71` using the hello-world image. It has Exited `(0)` 13 seconds ago where the `(0)` exit code means no error was produced during the runtime of the container.

### Now in order to understand what just happened behind the scenes, you'll have to get familiar with the Docker Architecture and three very fundamental concepts of containerization in general, which are as follows:

- Container
- Image
- Registry

## What is a Container?

### In the world of containerization, there can not be anything more fundamental than the concept of a container.

## The official Docker resources site says:

### A container is an abstraction at the application layer that packages code and dependencies together. Instead of virtualizing the entire physical machine, containers virtualize the host operating system only.

### You may consider containers to be the next generation of virtual machines.

### Just like virtual machines, containers are completely isolated environments from the host system as well as from each other. They are also a lot lighter than the traditional virtual machine, so a large number of containers can be run simultaneously without affecting the performance of the host system.‌

### Containers and virtual machines are actually different ways of virtualizing your physical hardware. The main difference between these two is the method of virtualization.

### Virtual machines are usually created and managed by a program known as a hypervisor, like Oracle VM VirtualBox, VMware Workstation, KVM, Microsoft Hyper-V and so on. This hypervisor program usually sits between the host operating system and the virtual machines to act as a medium of communication.

### Each virtual machine comes with its own guest operating system which is just as heavy as the host operating system.

### The application running inside a virtual machine communicates with the guest operating system, which talks to the hypervisor, which then in turn talks to the host operating system to allocate necessary resources from the physical infrastructure to the running application.

### As you can see, there is a long chain of communication between applications running inside virtual machines and the physical infrastructure. The application running inside the virtual machine may take only a small amount of resources, but the guest operating system adds a noticeable overhead.

### Unlike a virtual machine, a container does the job of virtualization in a smarter way. Instead of having a complete guest operating system inside a container, it just utilizes the host operating system via the container runtime while maintaining isolation – just like a traditional virtual machine.

### The container runtime, that is Docker, sits between the containers and the host operating system instead of a hypervisor. The containers then communicate with the container runtime which then communicates with the host operating system to get necessary resources from the physical infrastructure.

### As a result of eliminating the entire guest operating system layer, containers are much lighter and less resource-hogging than traditional virtual machines.

### As you know we are using Windows machine, you'll find out that all the containers use the WSL2 kernel. It happens because WSL2 acts as the back-end for Docker on Windows. On macOS the default back-end is a VM running on HyperKit hypervisor.
