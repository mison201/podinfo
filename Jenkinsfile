pipeline {
    agent any
    environment {
        GO111MODULE = 'on'
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build Dockerfile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}