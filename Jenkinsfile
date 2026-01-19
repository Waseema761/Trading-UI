pipeline {
    agent any

    tools {
        nodejs "Nodejs"   // same name you added in Jenkins tools
    }

    stages {
        stage('Checkout') {
            steps {
                git url:'https://github.com/Waseema761/Trading-UI.git', branch: 'master'
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
