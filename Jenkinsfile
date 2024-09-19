pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Stage 1: Build'
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Tests') {
            steps {
                echo 'Stage 2: Tests'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Stage 5: Deploy'
            }
        }
        stage('Release') {
            steps {
                echo 'Stage 6: Release'
            }
        }
        stage('Monitoring and Alerting') {
            steps {
                echo 'Stage 7: Monitoring and Alerting'
            }
        }
    }
}
