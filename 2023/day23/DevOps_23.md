# Day 23 — Jenkins Freestyle Project for DevOps Engineers.
## Tasks:

### **What is CI/CD?**
CI or Continuous Integration is the practice of automating the integration of code changes from multiple developers into a single codebase. It is a software development practice where the developers commit their work frequently into the central code repository (Github or Stash). Then there are automated tools that build the newly committed code and do a code review, etc as required upon integration. The key goals of Continuous Integration are to find and address bugs quicker, make the process of integrating code across a team of developers easier, improve software quality and reduce the time it takes to release new feature updates.
CD or Continuous Delivery is carried out after Continuous Integration to make sure that we can release new changes to our customers quickly in an error-free way. This includes running integration and regression tests in the staging area (similar to the production environment) so that the final release is not broken in production. It ensures to automate the release process so that we have a release-ready product at all times and we can deploy our application at any point in time.
### **What Is a Build Job?**
A Jenkins build job contains the configuration for automating a specific task or step in the application building process. These tasks include gathering dependencies, compiling, archiving, or transforming code, and testing and deploying code in different environments.

Jenkins supports several types of build jobs, such as freestyle projects, pipelines, multi-configuration projects, folders, multibranch pipelines, and organization folders.

### **What is Freestyle Projects ??**
A freestyle project in Jenkins is a type of project that allows you to build, test, and deploy software using a variety of different options and configurations.

## Task-01
### **Create a agent for your app. ( which you deployed from docker in earlier task)**
### **Create a new Jenkins freestyle project for your app.**
### **In the “Build” section of the project, add a build step to run the “docker build” command to build the image for the container.**
### **Add a second step to run the “docker run” command to start a container using the image created in step 3.**

1. Log in to your Jenkins instance and click on the “New Item” button.
2. Give your project a name “Django-todo-delivery” , select “Freestyle project” as the type, and click on the “OK” button.
3. Add your GitHub project URL.
4. In the “Build” section, click on the “Add build step” button and select “Execute shell” option.
5. In the “Command” field, enter the following command:
```
echo "Building"
docker build . -t django-todo
docker run -d --name django-ctr -p 8001:8001 django-todo:latest
```
To view the console output of a Jenkins build, follow these steps:

Go to the Jenkins dashboard and select the project that you want to view the console output for.

Click on the build number of the build that you want to view the console output for.

In the build details page, you will see a button named “Console Output”. Click on the button to view the console output.

The console output will show you the output of the build steps, including the output of any shell commands that were run as part of the build.

![1](https://user-images.githubusercontent.com/121767243/216815530-efc110f0-b929-4b51-8eb9-541104fd0b50.png)

Set the inbound rule on AWS and access the app at “public-ip:8001”

![1111111111111](https://user-images.githubusercontent.com/121767243/216815620-8f3520fd-4184-4312-b03e-074e1d0c36a2.png)

## Task-02
### **Create Jenkins project to run “docker-compose up -d” command to start the multiple containers defined in the compose file**
### **Set up a cleanup step in the Jenkins project to run “docker-compose down” command to stop and remove the containers defined in the compose file.**
1. Log in to your Jenkins instance and click on the “New Item” button.
2. Give your project a name “Django-todo-delivery” , select “Freestyle project” as the type, and click on the “OK” button.
3. Add your GitHub project URL.
4. In the “Build” section, click on the “Add build step” button and select “Execute shell” option.
5. In the “Command” field, enter the following command:
```
echo "Building"
docker-compose down
docker-compose up -d
```
To view the console output of a Jenkins build, follow these steps:

Go to the Jenkins dashboard and select the project that you want to view the console output for.

Click on the build number of the build that you want to view the console output for.

In the build details page, you will see a button named “Console Output”. Click on the button to view the console output.

The console output will show you the output of the build steps, including the output of any shell commands that were run as part of the build.

![2](https://user-images.githubusercontent.com/121767243/216815545-ff1fdbc2-1565-436b-a6a9-3fd1325c4149.png)

Set the inbound rule on AWS and access the app at “public-ip:8001”

![22222222222222222](https://user-images.githubusercontent.com/121767243/216815630-7af52ab5-1cbe-4a07-851e-ca012cc6d4f3.png)
