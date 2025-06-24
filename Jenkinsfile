pipeline {
    agent any

    tools {
        nodejs 'NodeJS'  // This should match the name you configured in Global Tool Configuration
    }

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Install npm dependencies
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Run tests (if any)
                    sh 'npm test'  // This assumes you have a test script in package.json
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Optionally, run a build step if needed
                    sh 'npm run build'  // If you have a build script in package.json
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    // Run the application, typically using npm start or another command
                    sh 'npm start'  // Or use any other command to start your app
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
