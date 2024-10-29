pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/anishsharma2277/MERN_Stack_Project_Ecommerce_Hayroo.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    // Build your Docker image
                    sh 'docker build -t your_image_name .'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Add your testing commands here
                    echo 'Testing...'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Run the Docker container
                    sh 'docker run -d -p 80:80 your_image_name'
                }
            }
        }
    }
}
