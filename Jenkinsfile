pipeline {
    agent {
        docker {
            image 'node:16'  // or 'node:18' if needed
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}
