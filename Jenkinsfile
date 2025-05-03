pipeline {
    agent any

    environment {
        IMAGE_NAME = 'srilakshmi21/nginxdockermay3'
        DOCKER_CREDENTIALS_ID = 'docker-hub'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/srilakshmi-2021/nginxDockerMay3.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}:latest")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        docker.image("${IMAGE_NAME}:latest").push()
                    }
                }
            }
        }
    }
}

