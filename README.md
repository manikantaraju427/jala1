# jala1
### Project Description:###
Build CI / CD Pipeline using Jenkins and deploy the real world Web Application in AWS Cloud
Goals:
CI/CD Pipelines will help you learn
server automation, continuous integration, building pipelines, configuration of tools, automated
testing, code quality improvement, and distributed systems in Jenkins through intensive, handson practical assignments.
Technologies Used:-
1. Jenkins
2. Groovy
3. AWS Cloud
4. Git
5. Docker

6. Steps:
1. Create jenkins file using our in-house code repo [should be cloned from
git/bitbucket]
2. Create Docker file in the same repository
3. Build-Docker image with tagging as build version, unit test cases should pass if
any for the code
4. The Image should be available in ECR with build version as TAG
5. The Docker Image should be deployed to EC2 Machine
6. The EC2 Machine Need to open specific Inbound Port and restrict Access only for
admin user to login
7. Jenkins Jobs should do validation and display successful message
8. Report should be sent to e-mail and it should contain status of each JOB
9. Domain should be registered with AWS



### project ###
### Step 1: Create a Simple Node.js Web Application
Created a new directory for my project in ubuntu server : 

$mkdir hello-world-app

$cd hello-world-app

Created a package.json file for my Node.js application:

$vi package.json

{
  "name": "hello-world-app",
  
  "version": "1.0.0",
  
  "description": "A simple Hello World web application",
  
  "main": "app.js",
  
  "scripts": {
  
    "start": "node app.js"
    
  },
 
  "author": "Your Name",
  
  "license": "MIT",
  
  "dependencies": {
  
    "express": "^4.17.1"
    
  }
  
}


# Create a app.js file

$vi app.js

const express = require('express');
const app = express();
const port = process.env.PORT || 3000;

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(port, () => {
  console.log(`Server is running on port ${port}`);
});


### Installed the Express.js framework, which we'll use to create a basic web server:

# step 1: Install Node.js and npm

$sudo apt update

$sudo apt install nodejs npm

Verified that Node.js and npm were installed successfully:

$node -v

$npm -v       

 installed 
Now that npm is successfully installed, than  install the Express.js framework and run my "Hello, World!" application:

In  project directory
# Step 2: Install Express.js and Run Application

$npm install express

After installing Express.js, i can start application:

$node app.js      (This command will start my Node.js application )

Server is running on port 3000

http://100.25.151.1/:3000     run  google  web browse

Hello, World! this is jala project 1 by manikanta raju dibbidi   ( out put)

# Push Code to GitHub 

 $git init

$git add .

 $git commit -m "commiting"

 $git push origin main

### Access the Jenkins Workspace:

Log in to  Jenkins server   Navigate to the Project Workspace:

In the Jenkins dashboard, find and click on my project/job's name to access its workspace.

Set up a Jenkins pipeline to automate the deployment of a real-world web application to AWS. The pipeline consists of several stages, each with specific tasks.
Clone the Code Repository:

The Jenkins pipeline starts by checking out the code from  code repository. The repository should be hosted on Github

### Dockerfile Creation:

Create a Dockerfile within the same code repository. This file is used to define the instructions for building a Docker image of  web application.
Build Docker Image: 

In the "Build" stage, Jenkins builds a Docker image using the Dockerfile. It also ensures that unit tests, if any, pass successfully.
Push Docker Image to ECR:

In the "Push Docker Image to ECR" stage, the Docker image is pushed to Amazon Elastic Container Registry (ECR). This step requires AWS credentials for authentication.

$aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 400558793627.dkr.ecr.us-east-1.amazonaws.com

$docker tag my-web-app:latest 400558793627.dkr.ecr.us-east-1.amazonaws.com/jala-project:latest

$docker push 400558793627.dkr.ecr.us-east-1.amazonaws.com/jala-project:latest

# Deploy to EC2 Machine:

The "Deploy to EC2" stage is responsible for deploying the Docker image to an Amazon EC2 instance. It connects to the EC2 instance using SSH.

# Open Specific Inbound Port on EC2:

The EC2 instance opens a specific inbound port, allowing access only to an admin user for security purposes.
Validation and Success Message:

# Jenkins performs validation tasks as part of the pipeline and displays a successful message if all stages are completed successfully.

# Email Notification:

The pipeline is configured to send email notifications. If any stage fails, an email notification will be sent containing the status of each job.

# Domain Registration with AWS:

Register a domain with AWS to make  web application accessible via a custom domain name. The specific steps for domain registration may vary.

# note

1)this is free tier account based my budget issues iam not afford to buy Domain names 

2) ec2 instance also terminatted part of free tier

3)thats why every step of my project screenshots uploaded in GITHUB account with project code 




















