pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/anishsharma2277/MERN_Stack_Project_Ecommerce_Hayroo.git'
        IMAGE_NAME = 'anishsharma13/hayroo-ecommerce'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'your-github-credentials-id', url: "${REPO_URL}"
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t ${IMAGE_NAME} .'
                }
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', 
                 usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    sh 'docker push ${IMAGE_NAME}'
                }
            }
        }

        stage('Deploy Application') {
            steps {
                script {
                    echo 'Deployment steps go here. For example, running docker-compose or kubectl commands.'
                }
            }
        }
    }
}
