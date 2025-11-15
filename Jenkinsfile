pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/cekzakyiriansyah/Proyek_bnsp.git'
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
        success {
            echo "SUCCESS"
            bat """
            curl -H "Content-Type: application/json" ^
            -X POST ^
            -d "{\\"content\\": \\"✅ Build SUCCESS dari Jenkins!\\", \\"username\\": \\"JenkinsBot\\"}" ^
            "https://discord.com/api/webhooks/1426469908967063636/NNpNFjy7K4PtPbZ5Hz74RAwJ-jTiYVCNXNRqczTif0NZhik9bhQrb2cLHdDoVyoRcCJO"
            """
        }

        failure {
            echo "FAILED"
            bat """
            curl -H "Content-Type: application/json" ^
            -X POST ^
            -d "{\\"content\\": \\"❌ Build FAILED dari Jenkins!\\", \\"username\\": \\"JenkinsBot\\"}" ^
            "https://discord.com/api/webhooks/1426469908967063636/NNpNFjy7K4PtPbZ5Hz74RAwJ-jTiYVCNXNRqczTif0NZhik9bhQrb2cLHdDoVyoRcCJO"
            """
        }
    }
}
