pipeline {
    agent any

    tools {
        nodejs "node23"  // Make sure this matches the name in Global Tool Configuration
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

        // stage('Test') {
        //     steps {
        //         sh 'npm test'
        //     }
        // }
    }
}
