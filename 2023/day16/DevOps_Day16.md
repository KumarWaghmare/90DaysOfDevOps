# Day 16 — Docker for DevOps Engineers
## Tasks:

### **Docker**

Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

### **1. Use the docker run command to start a new container and interact with it through the command line. [Hint: docker run hello-world].**

The “docker run” command is used to start a new container from an image. For example, to start a new container from the “hello-world” image and interact with it through the command line, you can run the following command:
```
docker run hello-world
```
![1 (1)](https://user-images.githubusercontent.com/121767243/213547873-ceea5da3-71ee-4fb0-bc30-bb640193394f.png)

### **2. Use the docker inspect command to view detailed information about a container or image.**

The “docker inspect” command is used to view detailed information about a container or image. For example, to view information about a container, you can run the following command:
```
docker inspect Container_ID
```
This will return a JSON object containing various information about the container, such as its ID, name, state, network settings, and more.

![2](https://user-images.githubusercontent.com/121767243/213548079-fcda3697-ee66-4ab4-be45-0b4c84da87cd.png)

### **3. Use the docker port command to list the port mappings for a container.**

To run the Jenkins container, you first need to have the Jenkins image available on your local system. You can download the image by running the following command:
```
docker pull jenkins/jenkins
```
![3](https://user-images.githubusercontent.com/121767243/213548214-79f7a044-a790-4bdb-ae1a-ed8ec780ad17.png)

To start a new container from the “jenkins” image and interact with it through the command line, you can run the following command:
```
sudo docker run --name my-jenkins -d -p 8080:8080 -v jenkins_home:/var/jenkins_home jenkins/jenkins
```
This command will run the Jenkins container with the name “my-jenkins” in detached mode (-d), map the host's port 8080 to the container's port 8080 (-p 8080:8080) and also create a volume named “jenkins_home” and maps it to the container's “/var/jenkins_home” folder.

![3 1](https://user-images.githubusercontent.com/121767243/213548352-4e000b84-97ba-4df9-b137-a6adc5344036.png)

The “docker port” command is used to list the port mappings for a container. For example, to list the port mappings for a container, you can run the following command:
```
docker port Container_ID
```
This will return the ports that are exposed by the container and mapped to host machine ports.

![3 2](https://user-images.githubusercontent.com/121767243/213548436-94591138-0d0c-4074-95e0-f8cf2f539cc0.png)

### **4. Use the docker stats command to view resource usage statistics for one or more containers.**

The “docker stats” command is used to view resource usage statistics for one or more containers. For example, to view statistics for a container, you can run the following command:
```
docker stats Container_ID
```
This will return real-time statistics for the container, including CPU usage, memory usage, and network traffic.

![4](https://user-images.githubusercontent.com/121767243/213548526-dcc83e54-e313-4816-887a-72b0caa58191.png)

### **5. Use the docker top command to view the processes running inside a container.**

The “docker top” command is used to view the processes running inside a container. For example, to view the processes running inside a container, you can run the following command:
```
docker top Container_ID
```
This will return a list of processes running inside the container, including the process ID, user, and command.

![5](https://user-images.githubusercontent.com/121767243/213548635-147f6a1c-98e9-48e5-a0d5-d78538497b47.png)

### **6. Use the docker save command to save an image to a tar archive and then use the docker load command to load an image from a tar archive.**

To save the “jenkins/jenkins” image to a tar archive, you can run the following command:
```
docker save jenkins/jenkins -o jenkins.tar
```
To load an image from the “jenkins.tar” archive, you can run the following command:
```
docker load -i jenkins.tar
```
This will load the image from the specified tar archive file and add it to your local image repository.

![6](https://user-images.githubusercontent.com/121767243/213548742-19805fe8-a06b-4efc-865f-8d0a48c5ff4d.png)
