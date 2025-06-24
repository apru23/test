pipeline {
    agent any
    
    environment {
        NODE_HOME = tool name: 'nodejs', type: 'NodeJS'
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
                    // Here you could add tests if needed
                    echo 'Running tests...'
                    // Example: sh 'npm test'
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    // Start the application
                    sh 'npm start'
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up after the run...'
            // Clean up if necessary
        }

        success {
            echo 'Build succeeded.'
        }

        failure {
            echo 'Build failed.'
        }
    }
}

