pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/username/repo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building on Windows...'
            }
        }

        stage('Test') {
            steps {
                bat 'npm install'
                bat 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying on Windows...'
            }
        }
    }

    post {
        success { echo "SUCCESS" }
        failure { echo "FAILED" }
    }
}
