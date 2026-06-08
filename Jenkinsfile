pipeline {

    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ishu1225/nginx-app:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push ishu1225/nginx-app:v1'
            }
        }

        stage('Deploy Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yml'
                sh 'kubectl apply -f service.yml'
            }
        }
    }
}