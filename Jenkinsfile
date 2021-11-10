pipeline {
    agent any
    environment {
        GO111MODULE = 'on'
    }
    stages {
        stage('Build FE') {
            steps {
                sh 'helm repo add podinfo https://github.com/mison201/podinfo'
                sh 'helm upgrade --install --wait frontend --namespace test --set replicaCount=2 --set backend=http://backend-podinfo:9898/echo podinfo/podinfo'

            }
        }
        stage('Test FE') {
            steps {
                sh 'helm test frontend'
            }
        }
        stage('Build BE') {
             steps {
                sh 'helm upgrade --install --wait backend --namespace test --set redis.enabled=true podinfo/podinfo'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}