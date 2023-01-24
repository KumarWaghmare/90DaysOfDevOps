# Day 17 — Docker Project for DevOps Engineers
## Tasks:

### **Dockerfile**

Docker is a tool that makes it easy to run applications in containers. Containers are like small packages that hold everything an application needs to run. To create these containers, developers use something called a Dockerfile.

A Dockerfile is like a set of instructions for making a container. It tells Docker what base image to use, what commands to run, and what files to include. For example, if you were making a container for a website, the Dockerfile might tell Docker to use an official web server image, copy the files for your website into the container, and start the web server when the container starts.

### **1. Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)**
To build a Dockerfile for node.js, create a file named Dockerfile, write the following commands in the file:
```
FROM node:12.2.0-alpine
WORKDIR app
COPY . /app
RUN npm install
EXPOSE 8000
CMD ["node","app.js"]
```
### **2. Build the image using the Dockerfile and run the container**
To build the image, navigate to the directory containing the Dockerfile and run the following command:
```
docker build . -t node-todo
```
This will create an image with the tag “node-todo”. To run the container, use the following command:
```
docker run -d --name node-todo-container -p 8000:8000 node-todo:latest
```
### **3. Verify that the application is working as expected by accessing it in a web browser**
To verify that the application is working, you can access it in a web browser by going to “http://localhost:8000"

![111](https://user-images.githubusercontent.com/121767243/214230722-e0dac8c6-daf4-443f-bf81-2790d908ff12.png)


### **4. Push the image to a public or private repository (e.g. Docker Hub )**
To push the image to a public or private repository, you need to first log in to the repository using the “docker login” command, then you can tag the image by “docker tag node-todo kumarwaghmare/node-todo” command.

The command “docker tag node-todo kumarwaghmare/node-todo” is used to create a new tag (or label) for an existing Docker image. The first argument “node-todo” is the name of the existing image, and the second argument “kumarwaghmare/node-todo” is the new name and tag that will be given to the image. This new tag can be used to refer to the image in future commands, such as “docker push” or “docker run”. In this case, the new tag is in the format of ‘username/image-name’ which is a common practice for sharing images on Docker Hub.

Then use “docker push” command to push the image to dockerhub.

![222](https://user-images.githubusercontent.com/121767243/214230813-03ff0100-1d19-423b-a5c9-2272c47f7ae9.png)

![333](https://user-images.githubusercontent.com/121767243/214230854-57d575a6-ddaa-48ab-b0fe-063b6f2fe92c.png)

