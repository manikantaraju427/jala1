pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID = 'AKIAV2QZKEON6I2AV3M4'
        AWS_SECRET_ACCESS_KEY = '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'
        AWS_DEFAULT_REGION = 'us-east-1'
        DOCKER_IMAGE_REPO = 'jala-project'
        BUILD_VERSION = sh(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
        EC2_INSTANCE_IP = '18.233.166.38'
        DOCKER_IMAGE_NAME = "my-node-app:latest" // Specified Docker image name and tag
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t my-node-app:latest ."
                }
            }
        }

        stage('Push Docker Image to ECR') {
            steps {
                script {
                    sh "aws ecr get-login-password --region ${AWS_DEFAULT_REGION} | docker login --username AWS --password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"
                    sh "docker tag ${DOCKER_IMAGE_NAME} ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${DOCKER_IMAGE_REPO}:${BUILD_VERSION}"
                    sh "docker push ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${DOCKER_IMAGE_REPO}:${BUILD_VERSION}"
                }
            }
        }

        stage('Deploy to EC2') {
            steps {
                script {
                    sh "ssh -o StrictHostKeyChecking=no -i 'C:\\Users\\NANI\\Downloads\\keypair.pem' ubuntu@$EC2_INSTANCE_IP 'docker pull ${DOCKER_IMAGE_NAME}'"
                    sh "ssh -o StrictHostKeyChecking=no -i 'C:\\Users\\NANI\\Downloads\\keypair.pem' ubuntu@$EC2_INSTANCE_IP 'docker stop your-app-container || true'"
                    sh "ssh -o StrictHostKeyChecking=no -i 'C:\\Users\\NANI\\Downloads\\keypair.pem' ubuntu@$EC2_INSTANCE_IP 'docker rm your-app-container || true'"
                    sh "ssh -o StrictHostKeyChecking=no -i 'C:\\Users\\NANI\\Downloads\\keypair.pem' ubuntu@$EC2_INSTANCE_IP 'docker run -d --name your-app-container -p 80:80 ${DOCKER_IMAGE_NAME}'"
                }
            }
        }
    }
}

