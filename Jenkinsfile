
pipeline {
    agent any

    environment {
        APP_NAME = "tokentrail"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/harikamekala222/TokenTrail.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker compose ps'
            }
        }
    }

    post {
        success {
            echo 'TokenTrail deployed successfully!'
        }
        failure {
            echo 'Deployment failed. Check Jenkins console output.'
        }
    }
}
