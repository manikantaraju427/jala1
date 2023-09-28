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







