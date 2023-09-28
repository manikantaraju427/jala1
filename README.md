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

$node app.js      (This command will start your Node.js application )

Server is running on port 3000

http://100.25.151.1/:3000     run  google  web browse

Hello, World! this is jala project 1 by manikanta raju dibbidi   ( out put)

# Push Code to GitHub 






















