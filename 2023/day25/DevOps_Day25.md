# Day 25 Task: Complete Jenkins CI/CD Project - Continued with Documentation

## Introduction
This document outlines the steps for setting up Jenkins to automate the deployment of a GitHub repository to a remote server. With these instructions, you'll be able to set up a Jenkins job that will automatically deploy changes to your repository whenever they are pushed to GitHub.

## Prerequisites
Before you begin, make sure you have the following:
- A GitHub repository
- A remote server with a web server installed (e.g. Apache or Nginx)
- Jenkins installed on the remote server
- Git installed on the Jenkins server
- A Jenkins job set up to build the repository

## Cloning the repository

To clone the repository, follow these steps:

1. Open your terminal or command prompt.
2. Navigate to the directory where you want to clone the repository.
3. Run the following command:
```
git clone https://github.com/<username>/<repository>.git
```
Replace `<username>` and `<repository>` with the appropriate values for your repository.

## Adding webhooks

To add a webhook in Jenkins, follow these steps:

1. Open your Jenkins dashboard.
2. Go to the desired project's configuration page.
3. Scroll down to the "Build Triggers" section.
4. Check the "GitHub hook trigger for GITScm polling" checkbox.
5. Save the changes.

## Deployment

To deploy the application using Jenkins, follow these steps:

1. Open your Jenkins dashboard.
2. Go to the desired project's configuration page.
3. Scroll down to the "Build" section.
4. In the “Build” section, click on the “Add build step” button and select “Execute shell” option.
5. Configure the deployment settings as needed.
6. Save the changes.

Note: The exact steps for deployment may vary depending on the application server being used.

## Conclusion

By following the steps outlined in this guide, you should be able to clone the repository, add webhooks, and deploy the application using Jenkins.

