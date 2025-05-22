pipeline {
    agent any
	environment {
		dockerHome = tool 'myDoker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:PATH"
	}
    stages {
        stage('Checkuot') {
            steps {
                script {
                    sh 'mvn --version'
					sh 'docker version'

                }
                echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_TAG - $env.BUILD_TAG"
            }
        }
		stage ('compile') {
			steps {
				sh "mvn clean compile"
			}	
		}
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
        stage('Integration Test') {
            steps {
                sh "mvn failsafe:integration-test  failsafe:verify"
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