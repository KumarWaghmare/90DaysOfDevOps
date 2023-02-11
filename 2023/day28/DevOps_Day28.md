# Day 28 — Jenkins Agents
## Tasks
### Jenkins Master (Server)
Jenkins’s server or master node holds all key configurations. Jenkins master server is like a control server that orchestrates all the workflow defined in the pipelines. For example, scheduling a job, monitoring the jobs, etc.

### Jenkins Agent
An agent is typically a machine or container that connects to a Jenkins master and this agent that actually execute all the steps mentioned in a Job. When you create a Jenkins job, you have to assign an agent to it. Every agent has a label as a unique identifier.

When you trigger a Jenkins job from the master, the actual execution happens on the agent node that is configured in the job.

A single, monolithic Jenkins installation can work great for a small team with a relatively small number of projects. As your needs grow, however, it often becomes necessary to scale up. Jenkins provides a way to do this called “master to agent connection.” Instead of serving the Jenkins UI and running build jobs all on a single system, you can provide Jenkins with agents to handle the execution of jobs while the master serves the Jenkins UI and acts as a control node.


### Pre-requisites
Let’s say we’re starting with a fresh Ubuntu 22.04 Linux installation. To get an agent working make sure you install Java ( same version as jenkins master server ) and Docker on it.

Note:- While creating an agent, be sure to separate rights, permissions, and ownership for jenkins users.

## Task-01
### Create an agent by setting up a node on Jenkins
### Create a new AWS EC2 Instance and connect it to master(Where Jenkins is installed)
### The connection of master and agent requires SSH and the public-private key pair exchange.
### Verify its status under “Nodes” section.

**STEP-01**

* The connection of master and agent requires SSH and the public-private key pair exchange.
* In Master, you will do “ssh-keygen” to generate keys(public & private). Then use the command “cd .ssh” to go inside ssh directory. You will be able to see the contents of the directory.
* Now copy public key of master by running “cat id_rsa.pub” command.
**Note: “id_rsa” is the private key and “id_rsa.pub” is the public key**

![5](https://user-images.githubusercontent.com/121767243/218266571-85122f03-9acf-460e-b969-21e6c121d982.jpg)

**STEP-02**

* Log in to the Agent EC2 instance using SSH.
* Do “cd .ssh” and “authorized_keys” file will be visible.
* Copy the contents of the “id_rsa.pub” key to the “authorized_keys” file.

<img width="1280" alt="8" src="https://user-images.githubusercontent.com/121767243/218266590-0428a6f6-e370-48ea-999b-d74b3ac346cc.png">

**STEP-03**

* Log in to the Jenkins master server where Jenkins is installed.
* Go to “Manage Jenkins” and then click on “Manage Nodes.”
* Click on “New Node” to create a new agent node.
* Give a name to the node (e.g. “jenkins-agent”) and select the “Permanent Agent” option.
* Under “Remote Root Directory,” provide the path to the directory where you want to store the Jenkins build files.
* In the “Launch Method” section, select “Launch agent via SSH.”
* Enter the hostname or IP address of the newly created Agent.
* In the “Credentials” section, provide the SSH username and private key “id_rsa” of Jenkins-Master EC2 instance.
* Save the changes.

![2 5](https://user-images.githubusercontent.com/121767243/218266624-01c0a1c6-4e59-4429-8afe-6f3f168b0cdc.jpg)

* Verify that the new agent appears in the “Nodes” section.

<img width="1007" alt="2 2" src="https://user-images.githubusercontent.com/121767243/218266651-94770fa6-611d-46c0-9710-0dca4223b16b.png">

## Task-02
### Run your previous Jobs on the new agent
### Use labels for the agent, your master server should trigger builds for the agent server.
* Go to your Jenkins instance and click on the “New Item” button.
* Give your project a name, select “Freestyle project” as the type, and click on the “OK” button.
* Add your GitHub project URL.
* Select the option “Restrict where this project can be run” and in “Label Expression field”, give the label of already made agent.
* In the “Build” section, click on the “Add build step” button and select “Execute shell” option.
* In the “Command” field, enter the commands

![3 1](https://user-images.githubusercontent.com/121767243/218266670-a8519d99-3e2e-4de1-a736-9e570746e17b.jpg)

* Save and run the pipeline
### Console Output

<img width="1280" alt="4" src="https://user-images.githubusercontent.com/121767243/218266679-34521364-7c75-477e-8f6a-16c22ac6b5dd.png">

### Agent

<img width="1016" alt="2 3" src="https://user-images.githubusercontent.com/121767243/218266688-c5699837-19a2-4581-bcf5-8362c6268e3e.png">

* Set the inbound rule on AWS and access the app at “Agent’s public-ip:8000”

<img width="1280" alt="3" src="https://user-images.githubusercontent.com/121767243/218266699-bdd37555-ce10-44b9-a7dc-6c147c8dfdb7.png">

