pipeline {
    agent any

    environment {
        // Add any environment variables here
        NODE_HOME = '/usr/local/bin/node'  // Example path for Node.js
        PATH = "${env.NODE_HOME}:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Pulls the latest code from the repository
                git 'https://github.com/arpitarai67/Devops.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install npm dependencies
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run build command (production build in React)
                    sh 'npm run build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests (assuming you have a testing script defined)
                    sh 'npm test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add your deployment steps here
                    // For example, deploy to a server or cloud service
                    echo 'Deploying application...'
                }
            }
        }
    }

    post {
        success {
            // Actions to take if the build succeeds (e.g., notify success)
            echo 'Build and deploy succeeded!'
        }
        failure {
            // Actions to take if the build fails (e.g., notify failure)
            echo 'Build or deploy failed!'
        }
    }
}
