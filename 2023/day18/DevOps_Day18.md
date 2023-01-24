# Day 18 — Docker for DevOps Engineers
## Tasks:

### **Docker Compose**
Docker Compose is a tool that was developed to help define and share multi-container applications.

With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.

### **What is YAML?**
YAML is a data serialization language that is often used for writing configuration files. Depending on whom you ask, YAML stands for yet another markup language or YAML ain’t markup language (a recursive acronym), which emphasizes that YAML is for data, not documents.

YAML is a popular programming language because it is human-readable and easy to understand.

YAML files use a .yml or .yaml extension.

### **1. Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.**
The first line of the “docker-compose.yml” file specifies the version of the Compose file format. In this case, it is "3.3". This tells Docker Compose which version of the file format to use when interpreting the rest of the file.

The “services” section defines the services that make up the application. In this example, there are two services defined: “web” and “db”.

The “web” service is using the “nginx:latest” image and maps port 80 on the host to port 80 in the container. It means that the container will be accessible on port 80 of the host machine.

The “db” service is using the “mysql” image and maps port 3306 on the host to port 3306 in the container. It means that the container will be accessible on port 3306 of the host machine. It also sets an environment variable “MYSQL_ROOT_PASSWORD” to “test@123” which will be used as the root password for the mysql instance running in the container.
```
version : "3.3"
services:
  web:
    image: nginx:latest
    ports:
      - "80:80"
  db:
    image: mysql
    ports:
      - "3306:3306"
    environment:
      - "MYSQL_ROOT_PASSWORD=test@123"
```
Now to build and run your app with Compose use command:
```
docker compose up
```

![111](https://user-images.githubusercontent.com/121767243/214232516-1704b76f-60a4-4f98-96b6-8c9e73ea0248.png)

Now to run a command in a running container use command:
```
docker exec -it container_id bash
```

![222](https://user-images.githubusercontent.com/121767243/214232945-41157136-6f6e-4403-a3e0-5c5df29b6ee2.png)

### **2. Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user (Hint- Use “usermod” command to give user permission to docker). Make sure you reboot instance after giving permission to user.**
To pull an existing Docker image from Docker Hub and run it on your local machine, you can use the “docker pull” command followed by the image name.
```
docker pull nginx:latest
```

![333](https://user-images.githubusercontent.com/121767243/214233268-f8427bd2-a75a-4ef3-9197-c8dd8394b7c3.png)

### **3. Inspect the container’s running processes and exposed ports using the docker inspect command.**
To inspect the container’s running processes and exposed ports using the “docker inspect” command, you can use the following command:
```
docker inspect container_name
```

![444](https://user-images.githubusercontent.com/121767243/214233525-0c82f790-312f-4f5f-b814-e9fb592309a2.png)

### **4. Use the docker logs command to view the container’s log output.**
To view the container’s log output, you can use the “docker logs” command followed by the container id.
```
docker logs container_id
```

![555](https://user-images.githubusercontent.com/121767243/214233870-db1ff064-5b3b-4aad-aaf0-06e38e00cd16.png)

### **5. Use the docker stop and docker start commands to stop and start the container. Then use the docker rm command to remove the container when you’re done.**
To stop and start the container, you can use the “docker stop” and “docker start” commands followed by the container id. To remove the container when you’re done, you can use the “docker rm” command followed by the container id.
```
docker stop container_id
docker start container_id
docker rm container_id
```

![666](https://user-images.githubusercontent.com/121767243/214233928-9e5db93d-d1d6-481e-9cff-643fa89efce5.png)

