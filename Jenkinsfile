pipeline {
    agent any

    tools {
        nodejs "Node23"  // Use the Node.js version "Node23"
    }

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm  // Fetch the latest code from GitHub
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'  // Install dependencies
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'  // Build the project
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'  // Run tests
            }
        }

        stage('Start Application') {
            steps {
                sh 'npm start'  // Run the app (assuming you have a start script in package.json)
            }
        }
    }
}
