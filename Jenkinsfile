pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Specify the master branch
                git branch: 'master', url: 'https://github.com/anishsharma2277/MERN_Stack_Project_Ecommerce_Hayroo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script { it ->  // Explicitly define the closure parameter
                    // Add your Docker build commands here
                    // Example: sh 'docker build -t your-image-name .'
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script { it ->  // Explicitly define the closure parameter
                    // Add your Docker push commands here
                    // Example: sh 'docker push your-image-name'
                }
            }
        }
        stage('Deploy') {
            steps {
                script { it ->  // Explicitly define the closure parameter
                    // Add your deployment commands here
                }
            }
        }
    }
}
