pipeline {
    agent any

    environment {
        DOCKER_IMAGE = '23aparna/test'  // Replace with your Docker Hub username and repo
        DOCKER_CREDENTIALS = 'dockerhub_credentials'  // Replace with the credentials ID in Jenkins
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/apru23/test.git'  // Replace with your GitHub repository URL
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build(DOCKER_IMAGE)
                }
            }
        }

        stage('Push Docker Image to Docker Hub') {
            steps {
                script {
                    // Login to Docker Hub
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS) {
                        // Push the Docker image to Docker Hub
                        docker.image(DOCKER_IMAGE).push()
                    }
                }
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean up the workspace after the pipeline completes
        }
    }
}
