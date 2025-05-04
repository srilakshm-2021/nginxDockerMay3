pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('Docker')
    }

    stages {
        stage('Cloning Web Repository From BitBucket') {
            steps {
                script {
                    checkout scm
                }
            }
        }
    }
}
