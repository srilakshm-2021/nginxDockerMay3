pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('srilakshmi21')
	}

	stages {
		stage('Cloning Web Repository From BitBucket') {
            steps {
                script{
                checkout scm
                }
            }
        }

	}
