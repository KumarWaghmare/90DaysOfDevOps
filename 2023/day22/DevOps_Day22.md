# Day 22 — Getting Started with Jenkins
## Tasks:

### **What is Jenkins?**
Jenkins is an open source continuous integration-continuous delivery and deployment (CI/CD) automation software DevOps tool written in the Java programming language. It is used to implement CI/CD workflows, called pipelines.
Jenkins is a tool that is used for automation, and it is an open-source server that allows all the developers to build, test and deploy software. It works or runs on java as it is written in java. By using Jenkins we can make a continuous integration of projects(jobs) or end-to-endpoint automation.
Jenkins achieves Continuous Integration with the help of plugins. Plugins allow the integration of Various DevOps stages. If you want to integrate a particular tool, you need to install the plugins for that tool. For example Git, Maven 2 project, Amazon EC2, HTML publisher etc.
### **1. What you understood in Jenkin, write a small article in your own words.**
Jenkins is an open-source automation tool that helps developers to automate the building, testing, and deployment of software projects. It provides a user-friendly interface that allows users to create and manage jobs, which are essentially scripts or commands that run on a schedule or when triggered by an event. Jenkins also supports integration with a variety of tools and plugins, such as Git, Maven, and JUnit, to provide a complete continuous integration and continuous delivery (CI/CD) solution. With Jenkins, developers can easily automate repetitive tasks, catch errors early, and ensure that their code is always in a releasable state.

### **2. Create a freestyle pipeline to print “Hello World!!**
To create a freestyle pipeline in Jenkins, follow these steps:

Log in to your Jenkins instance and click on the “New Item” button.

Give your pipeline a name “Hello-World” and select “Freestyle project” as the type, then click on the “OK” button.

In the “Build” section, click on the “Add build step” button and select “Execute shell” option.

In the “Command” field, enter the following command:
```
echo "Day-22 : Getting Started with Jenkins"
echo "Hello World!!"
```
Click on the “Save” button to create the pipeline.

Click on the “Build Now” button to run the pipeline and see the output.

<img width="1279" alt="3" src="https://user-images.githubusercontent.com/121767243/216009884-243f61a3-95de-4ab5-a66e-98b4726de820.png">

This pipeline will execute a single build step which will print the message “Hello World!!” when pipeline is built.

<img width="1280" alt="4" src="https://user-images.githubusercontent.com/121767243/216009982-462844bc-3fac-4f82-902d-883afe61c9ca.png">


