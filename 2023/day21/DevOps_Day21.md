# Day 21 — Docker Important Interview Questions

### **1. What is the Difference between an Image, Container and Engine?**
An image is a pre-built and pre-configured software package that contains all the necessary dependencies and instructions for running a specific application or service. A container is an instance of an image, created at runtime with its own unique set of resources and file system. An engine is software that powers the creation and management of images and containers, such as Docker.

### **2. What is the Difference between the Docker command COPY vs ADD?**
The COPY command is used to copy files from the host system to the container, while the ADD command can do the same but also supports file compression and URL sources.

### **3. What is the Difference between the Docker command CMD vs RUN?**
The CMD command is used to specify the command that should be run when a container is started from the image, while the RUN command is used to execute commands during the image-building process.

### **4. How Will you reduce the size of the Docker image?**
To reduce the size of a Docker image, you can use multi-stage builds, remove unnecessary files and dependencies, and use smaller base images.

### **5. Why and when to use Docker?**
Docker is a containerization platform that allows developers to package, deploy and run applications in a consistent and isolated environment, ensuring consistency and reproducibility, isolation, portability, scalability, cost-effectiveness, microservices architecture and virtualization of legacy app, It is widely used in the development, testing, production, and CI/CD pipeline.

### **6. Explain the Docker components and how they interact with each other.**
Docker has several components, including the Docker daemon, which manages the creation and management of containers, the Docker client, which communicates with the daemon to issue commands, and the Docker registry, which stores and distributes images.

### **7. Explain the terminology: Docker Compose, Docker File, Docker Image, Docker Container.**
Docker Compose is a tool for defining and running multi-container applications. A Dockerfile is a script that contains instructions for building an image. A Docker image is a pre-built and pre-configured software package that can be used to create a container. A Docker container is an instance of an image, created at runtime.

### **8. In what real scenarios have you used Docker?**
I have used Docker in a variety of scenarios including development, CI/CD, microservices architecture, testing and staging, production, virtualization of legacy app, big data and data science environment. It allows for consistency and reproducibility in builds, easy scaling and management of applications, and efficient use of system resources.

### **9. Docker vs Hypervisor.**
Docker and hypervisors both enable multiple isolated environments to run on a single host, but they differ in how they achieve this isolation. A hypervisor creates virtual machines, each with its operating system, while Docker runs multiple containers on a single operating system.

### **10. What are the advantages and disadvantages of using docker?**
Advantages of using Docker include consistency and reproducibility in builds, easy scaling and management of applications, and efficient use of system resources. Disadvantages include a potential learning curve and increased complexity in certain situations.

### **11. What is a Docker namespace?**
A Docker namespace is a virtualized environment for certain system resources, such as network interfaces, that is used to isolate containers from one another.

### **12. What is a Docker registry?**
A Docker registry is a service that stores and distributes Docker images.

### **13. What is an entry point?**
An entry point is a command that is run when a container is started from an image.

### **14. How to implement CI/CD in Docker?**
To implement CI/CD in Docker, you can use a continuous integration tool to build and test images automatically, and then use a container orchestration tool to deploy and manage the containers in a production environment.

### **15. Will data on the container be lost when the docker container exits?**
Data on a container will be lost when the container exits, unless steps are taken to persist the data, such as by using a volume or bind mount.

### **16. What is a Docker swarm?**
A Docker Swarm is a native orchestration feature of Docker that allows you to create and manage a cluster of Docker engines called a swarm. This cluster enables you to schedule and manage the placement of containers across the swarm, allowing you to easily scale and manage your application. With a swarm, you can also perform rolling updates to your application, ensuring high availability and minimizing downtime. Additionally, a swarm allows you to load balance the traffic to your application, automatically distributing it across the available nodes in the swarm.

### **17. What are the docker commands for the following:**
**view running containers**
```
docker ps
```
**command to run the container under a specific name**
```
docker run --name <name> <image>
```
**command to export a docker**
```
docker export <container> > <filename>
```
**command to import an already existing docker image**
```
docker import <filename> <repository:tag>
```
**commands to delete a container**
```
docker rm <container>
```
**command to remove all stopped containers, unused networks, build caches, and dangling images?**
```
docker system prune
```
### **18. What are the common docker practices to reduce the size of Docker Images?**
Common practices to reduce the size of Docker images include: using multi-stage builds, removing unnecessary files and dependencies, using smaller base images, using a .dockerignore file, squashing multiple layers, using a caching mechanism, version pinning and using image scanning and vulnerability analysis tools. While these practices can help reduce the size of images, it’s important to consider the impact on the functionality of the application.
