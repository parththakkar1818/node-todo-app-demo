pipeline {
    agent any
    
    environment {
        DOCKER_CREDENTIALS = credentials('docker-hub-credentials')
        IMAGE_NAME = 'parth224/node-todo'
        DOCKER_TAG = 'latest'
    }
    
    stages {
        stage('Clone Code') {
            steps {
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                sh """
                sudo docker build -t ${IMAGE_NAME}:${DOCKER_TAG} .
                """
            }
        }

        stage('check Docker Image') {
            steps {
                // Build Docker image
                sh """
                sudo docker images .
                """
            }
        }


    }
}
