# Day 26 — Jenkins Declarative Pipeline
## Task
One of the most important parts of your DevOps and CICD journey is a Declarative Pipeline Syntax of Jenkins

### Some terms for your Knowledge
What is Pipeline — A pipeline is a collection of steps or jobs interlinked in a sequence.

Declarative: Declarative is a more recent and advanced implementation of a pipeline as a code.

Scripted: Scripted was the first and most traditional implementation of the pipeline as a code in Jenkins. It was designed as a general-purpose DSL (Domain Specific Language) built with Groovy.

### Why you should have a Pipeline
The definition of a Jenkins Pipeline is written into a text file (called a Jenkinsfile) which in turn can be committed to a project’s source control repository.
This is the foundation of "Pipeline-as-code"; treating the CD pipeline as a part of the application to be versioned and reviewed like any other code.

Creating a Jenkinsfile and committing it to source control provides a number of immediate benefits:

* Automatically creates a Pipeline build process for all branches and pull requests.
* Code review/iteration on the Pipeline (along with the remaining source code).
### Pipeline syntax
```
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // 
            }
        }
        stage('Test') { 
            steps {
                // 
            }
        }
        stage('Deploy') { 
            steps {
                // 
            }
        }
    }
}
```
## Task-01
### Create a New Job, this time select Pipeline instead of Freestyle Project.
### Follow the Official Jenkins Hello world example
### Complete the example using the Declarative pipeline
* Login to your Jenkins and Install the Docker Pipeline plugin through the Manage Jenkins > Manage Plugins page.
* In your Jenkins instance and click on “New Item”.
* Enter a name for your job and select “Pipeline” as the project type.
* In the “Pipeline” section, select “Declarative” as the pipeline syntax.
* Copy and paste the pipeline script into the script editor.
```
Jenkinsfile (Declarative Pipeline)
/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'node:16.17.1-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
    }
}
```
* Save the job by clicking “Save”.
* Build the job by clicking “Build Now”.
* Check the Console Output to see the pipeline stages executing and the messages being echoed.

![1_8u77JWPzB1AC8cnm3lDYAQ](https://user-images.githubusercontent.com/121767243/218265918-a110757d-700a-4554-92fa-7cec150ab2ca.png)
