## What is a Docker Image?

### Images are multi-layered self-contained files that act as the template for creating containers. They are like a frozen, read-only copy of a container. Images can be exchanged through registries.

### In the past, different container engines had different image formats. But later on, the Open Container Initiative (OCI) defined a standard specification for container images which is complied by the major containerization engines out there. This means that an image built with Docker can be used with another runtime like Podman without any additional configurations.

### Containers are just images in running state. When you obtain an image from the internet and run a container using that image, you essentially create another temporary writable layer on top of the previous read-only ones.

### This concept will become a lot clearer in upcoming sections of these lessons. But for now, just keep in mind that `images` are `multi-layered` `read-only files` carrying your application in a desired state inside them.

## What is a Docker Registry?

### An image registry is a centralized place where you can upload your images and can also download images created by others. Docker Hub is the default public registry for Docker. Another very popular image registry is Quay by Red Hat.

### Throughout these lessons I will be using Docker Hub as my registry of choice.

### You can share any number of public images on Docker Hub for free. People around the world will be able to download them and use them freely.

### Apart from Docker Hub or Quay, you can also create your own image registry for hosting private images. There is also a local registry that runs within your computer that caches images pulled from remote registries.
