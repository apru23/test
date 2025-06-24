pipeline {
    agent any
    tools {
        nodejs 'NodeJS'  // Make sure 'NodeJS' is set up in Jenkins Global Tools
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

        // Remove or comment out the 'Build' stage if it's not needed
        /* stage('Build') {
            steps {
                script {
                    // Run build (if any)
                    sh 'npm run build'
                }
            }
        } */

        stage('Run Application') {
            steps {
                script {
                    // Run the application, typically using npm start or another command
                    sh 'npm start'  // Or use any other command to start your app
                }
            }
        }
    }
}
