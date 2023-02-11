# Day 27 — Jenkins Declarative Pipeline with Docker
## Task
### Use your Docker Build and Run Knowledge
docker build — you can use sh 'docker build . -t <tag>' in your pipeline stage block to run the docker build command. (Make sure you have docker installed with correct permissions.

docker run: you can use sh 'docker run -d <image>' in your pipeline stage block to build the container.

How will the stages look
```
stages {
        stage('Build') {
            steps {
                sh 'docker build -t trainwithshubham/django-app:latest'
            }
        }
    }
```
## Task-01
### Create a docker-integrated Jenkins declarative pipeline
### Use the above-given syntax using sh inside the stage block
### You will face errors in case of running a job twice, as the docker container will be already created, so for that do task 2
## Task-02
### Create a docker-integrated Jenkins declarative pipeline using the docker groovy syntax inside the stage block.
### You won’t face errors, you can Follow this documentation
### Complete your previous projects using this Declarative pipeline approach


**To create a Jenkins declarative pipeline with Docker integration, follow these steps:**

* Create a new Jenkins pipeline job and choose “Declarative” as the pipeline type.
* In the pipeline script, define the stages that you want to run. In this case, you have two stages: “Build” and “Run”.
* Use the following pipeline script:
```
pipeline {
    agent any
    
    stages{
        stage('Code'){
            steps{
                git url: 'https://github.com/KumarWaghmare/Jenkins-Project.git', branch: 'master' 
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t kumarwaghmare/node-todo-test:latest .'
            }
        }
        stage('Run') {
            steps {
                sh 'docker run -d kumarwaghmare/node-todo-test:latest'
            }
        }
    }
}
```
* Save the pipeline and run the job. You should see the stages executing one by one and the Docker image being built and run as containers.
  
![1_W9Dj-9bRwMqUlv2GSZGxgg](https://user-images.githubusercontent.com/121767243/218266250-4719b7e7-7868-4814-a1db-a35621dd8e9b.png)

* Check the Console Output to see the pipeline stages executing.
 
![1_krfXNUWoPUj8zmUxApe90A](https://user-images.githubusercontent.com/121767243/218266269-3c3bd4b0-862c-4913-a4e4-71fa4d1c781b.png)

