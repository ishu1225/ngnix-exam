pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/ishu1225/nginx-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t ishu1225/nginx-app:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                bat 'docker push ishu1225/nginx-app:v1'
            }
        }

        stage('Deploy Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yml'
                bat 'kubectl apply -f service.yml'
            }
        }
    }
}