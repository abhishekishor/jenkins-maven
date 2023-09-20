# Jenkins Pipeline for Building and Archiving a Maven Project

![Jenkins-maven](https://github.com/abhishekishor/jenkins-maven/assets/121818867/0a75c184-3d99-4124-bf2b-15ca3c5dbc2d)

This Jenkins Pipeline script automates the process of checking out code from a Git repository, building it using Maven, and archiving the resulting WAR file.

Table of Contents
Introduction
Prerequisites
Maven Installation
Getting Started
Usage
Contributing
License
Introduction
This Jenkins Pipeline script is designed to streamline the process of building a Java project hosted on a Git repository using Maven and archiving the resulting WAR file. It can be used to automate the CI/CD process for Java web applications.

Prerequisites
Before setting up and running this Jenkins Pipeline, ensure that you have the following prerequisites in place:

Jenkins Server: Set up a Jenkins server with the necessary plugins installed.
Git: Ensure that Git is installed on your Jenkins server.
Maven: Install and configure Maven on your Jenkins server.
GitHub Repository: Create a GitHub repository that contains your Java project with a pom.xml file and the source code.
Maven Installation
Maven: Install and configure Maven on your Jenkins server. You can specify the Maven installation tool as "Maven-Tool" or use the name of your Maven tool installation in your Jenkins Pipeline configuration.

Here's how to configure the Maven tool in your Jenkins Pipeline:

Go to your Jenkins server's dashboard.

Click on "Manage Jenkins" in the left sidebar.

Select "Global Tool Configuration".

Scroll down to the "Maven" section.

Click on "Add Maven" to define a Maven installation.

Provide a name for the Maven installation, e.g., "Maven-Tool" or use an existing name if applicable.

Specify the Maven installation directory or let Jenkins install it automatically.

Save your configuration.

Now, in your Jenkins Pipeline script, use the specified Maven installation tool (e.g., "Maven-Tool") like this:

pipeline {
    agent any
    tools {
        maven 'Maven-Tool' // Use the name you specified in the Global Tool Configuration
    }
    stages {
        // ...
        stage("Maven Build") {
            steps {
                sh "mvn clean package"
            }
        }
        // ...
    }
}
Getting Started
Follow these steps to set up and run the Jenkins Pipeline:

Clone this repository to your local machine or Jenkins server.

Create a new Jenkins Pipeline job and configure it to use this repository as the source.

In the pipeline configuration, specify the Maven installation tool as "Maven-Tool" or the name of your Maven tool installation.

Save the pipeline configuration.

Run the pipeline, and it will execute the following stages:

Git Checkout: Check out the code from the specified GitHub repository.
Maven Build: Build the Java project using Maven. The mvn clean package command is used here, but you can modify it according to your project's build requirements.
Archive Artifact: Archive the resulting WAR file located in the target directory.
Usage
This Jenkins Pipeline can be used as a template for building and archiving Java web applications. Customize it to fit your specific project requirements.

Contributing
Contributions are welcome! If you have suggestions, improvements, or bug fixes, please feel free to open an issue or submit a pull request.

License
This project is licensed under the MIT License.
