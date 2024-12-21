pipeline {
    agent { label 'devops1-asri' }

    stages {
        stage('build Apps') {
            steps {
               sh '''cd app
               npm install'''
            }
        }

        stage('Testing Apps') {
            steps {
                echo 'Testing Apps'
            }
        }

        stage('Code Scan') {
            steps {
                echo 'Code Scan'
            }
        }

        stage('Build Image') {
            steps {
                echo 'Build Image'
            }
        }

        stage('Push Image') {
            steps {
                echo 'Push Image'
            }
        }

        stage('Deploy Apps') {
            steps {
                echo 'Deploy Apps'
            }
        }
    }
}