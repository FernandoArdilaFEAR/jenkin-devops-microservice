pipeline {
    agent any
	environment {
		dockerHome = tool 'myDoker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:PATH"
	}
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'mvn --version'
					sh 'docker version'

                }
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
    post {
        success {
            echo 'done'
        }
        failure {
            echo 'crashed'
        }
    }
}