pipeline {
		// agent any
		agent { docker {image 'node: 3.20'}}
		stages {
			stage('Build') {
				steps {
					sh 'node --version'
					echo "Build"
				}
			}
			stage('Test') {
				steps {
					echo "Test"
				}
			}
			stage('Integration Test') {
				steps {
					echo "Integration Test"
				}
			}
		}
	post{
		success {
			echo 'done'
		}
		failure {
			echo 'crashed'
		}
	}		
}
