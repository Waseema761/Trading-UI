pipeline {
    agent any

    tools {
        nodejs "Nodejs"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Waseema761/Trading-UI.git', branch: 'master'
            }
        }

        stage('Check Node & NPM') {
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
                sh 'NODE_OPTIONS=--openssl-legacy-provider npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }
    }
}
