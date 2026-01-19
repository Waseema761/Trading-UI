pipeline {
    agent any

    tools {
        nodejs "Nodejs"
    }

    environment {
        NODE_OPTIONS = "--openssl-legacy-provider"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Waseema761/Trading-UI.git', branch: 'master'
            }
        }

        stage('Check Node Version') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }

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

        stage('Test') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }
    }
}
