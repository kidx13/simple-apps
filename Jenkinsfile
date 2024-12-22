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
                sh '''cd app
               npm test'''
            }
        }

        stage('Code Scan') {
            steps {
               sh '''cd app
sonar-scanner   -Dsonar.projectKey=simple-apps   -Dsonar.sources=.   -Dsonar.host.url=http://172.23.1.11:9000   -Dsonar.login=sqp_f82727411697a53518e9ce4f32e1de25884575a1'''
            }
        }

        stage('Build Image') {
            steps {
                 sh '''cd app
               docker compose build'''
            }
        }

        stage('Push Image') {
            steps {
                  sh '''cd app
               docker compose push'''
            }
        }

        stage('Deploy Apps') {
            steps {
                     sh '''cd app
               docker compose up -d'''
            }
        }
    }
}