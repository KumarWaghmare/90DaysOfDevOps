# Day 19 — Docker for DevOps Engineers
## Docker-Compose and Docker Volume
### **Docker Volume**
Docker allows you to create something called volumes. Volumes are like separate storage areas that can be accessed by containers. They allow you to store data, like a database, outside the container, so it doesn’t get deleted when the container is deleted. You can also mount from the same volume and create more containers having same data.

### **Docker Network**
Docker allows you to create virtual spaces called networks, where you can connect multiple containers (small packages that hold all the necessary files for a specific application to run) together. This way, the containers can communicate with each other and with the host machine (the computer on which the Docker is installed). When we run a container, it has its own storage space that is only accessible by that specific container. If we want to share that storage space with other containers, we can’t do that.

## Task-1
### **Create a multi-container docker-compose file which will bring UP and bring DOWN containers in a single shot (Example — Create application and database container)**
The first step is to create a “docker-compose.yml” file that defines the multi-container application.
```
version : "3.3"
services :
  web :
    build : .
    ports :
        - "8000-8003:3000"
  db:
    image : mysql
    ports :
       - "3306:3306"
    environment :
      MYSQL_ROOT_PASSWORD : "test@123"
```
### **Use the “docker-compose up” command with the “-d” flag to start a multi-container application in detached mode. Use the “docker-compose scale” command to increase or decrease the number of replicas for a specific service.**
The following command starts and runs a multi-container Docker application in the background using a “docker-compose” file, scaling the number of instances of the “web” service to 3.
```
docker-compose up --scale web=3 -d
```

![111](https://user-images.githubusercontent.com/121767243/214311616-849fa748-6ab8-44eb-b114-6da72cf652c3.png)

### **Use the “docker-compose ps” command to view the status of all containers, and “docker-compose logs” to view the logs of a specific service.**

![222](https://user-images.githubusercontent.com/121767243/214311797-d7d6761c-ee4e-468b-a692-4c20a18b2493.png)

![333](https://user-images.githubusercontent.com/121767243/214311856-bdd44dc4-537f-40a9-9e5c-5a9f91aca8b6.png)

### **Use the “docker-compose down” command to stop and remove all containers, networks, and volumes associated with the application.**

![444](https://user-images.githubusercontent.com/121767243/214311985-4938f554-d659-4644-abe6-aae61f2ab52c.png)

## Task-2
### **Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.**
### **Create two or more containers that read and write data to the same volume using the “docker run --mount” command.**
### **Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.**
### **Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you’re done.**

Create a Volume directory and Docker image “todo-app”

<img width="821" alt="1" src="https://user-images.githubusercontent.com/121767243/214312239-4bae8dac-ca20-4c43-8af4-ba4216ebef92.png">

The following command line instructions is used to run a container using a specific image, list and stop a container, navigate to a directory, create a Docker volume and display its details. The volume is associated with a directory and its files.

<img width="1268" alt="2" src="https://user-images.githubusercontent.com/121767243/214312378-6b81a37f-e141-490a-baa3-f98b49c038a7.png">

The command “docker run -d -p 8001:8001 --mount source=react_django_vol,target=/app todo-app:latest” is used to run a container using the image “todo-app:latest” in detached mode. The option“-d” runs the container in the background, “-p 8001:8001” maps the host port 8001 to the container port 8001 and “--mount” flag is used to mount the volume “react_django_vol” to the container at the “/app” directory. The command “docker ps” lists the running containers and their details. The command “docker exec -it d69098e96337 bash” is used to execute a command in a running container and opens a shell terminal in the container.

**The above instructions show that the container is running with the volume mounted and any changes made inside the container will reflect on the host’s directory and vice versa.**

<img width="1189" alt="3" src="https://user-images.githubusercontent.com/121767243/214312483-86925494-21b3-49ea-af7c-1b02c6a85e42.png">
