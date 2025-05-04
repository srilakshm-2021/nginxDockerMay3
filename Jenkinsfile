pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('srilakshmi21')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t srilakshmi21/nginxdockermay3:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push srilakshmi21/nginxdockermay3:latest'
			}
		}
		stage('Pull') {

			steps {
				sh 'docker pull srilakshmi21/nginxdockermay3:latest'
			}
		}
		stage('deploy') {

			steps {
				sh 'docker run -itd  --name sunil1 srilakshmi21/nginxdockermay3:latest'
			}
		}
	}

}
