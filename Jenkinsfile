pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'node:20' // Base Docker image for building
        APP_NAME = 'my-app'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/saruni13/ecommerce-application.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.build("$APP_NAME:latest")
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.withRegistry('', 'dockerhub_credentials') {
                        docker.image("$APP_NAME:latest").push()
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // Example deployment step (modify based on your deployment needs)
                sh 'docker-compose up -d'
            }
        }
    }

    post {
        success {
            echo 'Pipeline successful!'
        }
        failure {
            echo 'Pipeline failed :('
        }
    }
}