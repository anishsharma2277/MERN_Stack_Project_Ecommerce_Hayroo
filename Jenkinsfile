pipeline {
    agent any
    environment {
        DOCKER_HUB_CREDENTIALS = credentials('docker-credentials-id')
    }
    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'your-github-credentials-id', url: 'https://github.com/anishsharma2277/MERN_Stack_Project_Ecommerce_Hayroo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t your-docker-image-name .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                bat 'docker login -u %DOCKER_HUB_CREDENTIALS_USR% -p %DOCKER_HUB_CREDENTIALS_PSW%'
            }
        }
        stage('Push Docker Image') {
            steps {
                bat 'docker push your-docker-image-name'
            }
        }
        stage('Deploy Application') {
            steps {
                bat 'your-deployment-command'
            }
        }
    }
}
