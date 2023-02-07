# Day 24 — Complete Jenkins CI/CD Project
## **Tasks:**

## **Task-01**
#### Fork this repository:
#### Create a connection to your Jenkins job and your GitHub Repository via GitHub Integration.
#### Read About GitHub Webhooks and make sure you have CICD setup
* Go to the GitHub repository (https://github.com/LondheShubham153/node-todo-cicd) and click on the “Fork” button to create a copy of the repository in your GitHub account.

* Next, set up a Jenkins job for the forked repository. You can do this by logging into your Jenkins instance, clicking on “New Item,” giving it a name “node-todo-cicd”, and selecting “Freestyle project”

* Under the “Source Code Management” section, select “Git” and enter the URL of your forked repository.

* Next, set up the GitHub integration by installing the GitHub plugin in Jenkins and configuring it in the “GitHub plugin” section of the job configuration.

* In the “Build” section, click on the “Add build step” button and select “Execute shell” option.

* In the “Command” field, enter the following command
```
echo "Hello"
```
* To view the console output of a Jenkins build, follow these steps:

* Go to the Jenkins dashboard and select the project that you want to view the console output for.

* Click on the build number of the build that you want to view the console output for.

* In the build details page, you will see a button named “Console Output”. Click on the button to view the console output.

* The console output will show you the output of the build steps, including the output of any shell commands that were run as part of the build.

<img width="1277" alt="1" src="https://user-images.githubusercontent.com/121767243/217178906-80514325-bf6a-4d6a-8ad5-2b79662831df.png">

### Webhook
A webhook is a mechanism for sending an HTTP request to a URL when a specific event occurs. It is used for real-time notifications and to allow integration between different systems.

* Set up the GitHub integration by installing the GitHub plugin in Jenkins.

![2023-02-06 15 21 19](https://user-images.githubusercontent.com/121767243/217179430-670929e7-24ab-418b-a0e2-56c49c3e8e0b.jpg)

* Create a new pipeline job in Jenkins or select an existing pipeline job.
* In the Jenkins job configuration page, scroll down to the “Build Triggers” section.
* Check the “GitHub hook trigger for GITScm polling” option.
* Save the job configuration.

<img width="871" alt="Screenshot 2023-02-06 154101" src="https://user-images.githubusercontent.com/121767243/217179688-60ebdd6f-b9fa-4adb-af9d-532173d9df1e.png">

* To set up the webhook, go to your forked repository’s settings, select “Webhooks,” and add a new webhook pointing to your Jenkins instance.
* In the “Payload URL” field, enter the URL for the Jenkins webhook, which should be in the following format: http://<JENKINS_URL>/github-webhook/.
Choose the “application/json” content type.
* Select the events that will trigger the webhook, such as “push” or “pull request”.
* Save the webhook.

<img width="1236" alt="Screenshot 2023-02-06 152847" src="https://user-images.githubusercontent.com/121767243/217179856-ebcfe16c-042e-4d95-adbe-1ac19fb6d920.png">

<img width="847" alt="Screenshot 2023-02-06 153937" src="https://user-images.githubusercontent.com/121767243/217179926-c9400bf8-e072-4d0b-bdf2-eda91a37d260.png">

Finally, make sure that your Jenkins job is properly set up for continuous integration and delivery by checking the build triggers and post-build actions.

Now, whenever a push is made to the GitHub repository associated with the Jenkins job, the pipeline will be automatically triggered.

![20230206_153715 (1)](https://user-images.githubusercontent.com/121767243/217181816-fe6c6d87-68d5-4768-b6a1-6faa746af8f2.gif)

## **Task-02**
#### In the Execute shell run the application using Docker compose
#### You will have to make a Docker Compose file for this Project (Can be a good open source contribution)
#### Run the project
* Create a Docker Compose file for the project. The file should specify the services required for the application and the Docker images for each service.
* In the Jenkins job, add an “Execute shell” build step to run the application using Docker Compose. The command to run would be:
```
echo "Building"
docker-compose down
docker-compose up -d
```
* Save the changes to the job configuration and run a build. If everything is set up correctly, the application should start running within Docker containers.

<img width="1280" alt="4" src="https://user-images.githubusercontent.com/121767243/217181153-79f616b1-f0a6-4fde-9dca-eb27606fa2e9.png">

View the console output of a Jenkins build

<img width="1256" alt="2" src="https://user-images.githubusercontent.com/121767243/217181324-c86e4962-e1ec-4ebf-9eb6-9017bc014aaa.png">

Set the inbound rule on AWS and access the app at “public-ip:8000”

<img width="1280" alt="3" src="https://user-images.githubusercontent.com/121767243/217181383-f5f276d6-edc6-4a4a-9ba1-9e685bea67c9.png">
