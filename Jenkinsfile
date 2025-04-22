pipeline {
    agent any
    
    environment {
        // Optional: Add your Node.js home path here
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://your-repository-url.git'  // Replace with your Git repo URL
            }
        }
        
        stage('Install Dependencies') {
            steps {
                dir('ecom-master') {  // Assuming your frontend is in the 'ecom-master' folder
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                dir('ecom-master') {
                    sh 'npm test -- --maxWorkers=1'  // Run tests with single worker for Jenkins
                }
            }
        }

        stage('Build') {
            steps {
                dir('ecom-master') {
                    sh 'npm run build'  // This will create a production-ready build of your app
                }
            }
        }

        stage('Deploy') {
            steps {
                // Example: Deploy to your server using SSH or any other method
                sh '''
                ssh user@yourserver.com "cd /path/to/project && git pull && npm install && npm run build"
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
