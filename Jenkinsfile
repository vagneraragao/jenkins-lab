pipeline {
	// agent any
	agent { docker { image 'maven:3.6.3'} } 
	stages {
		stage('Build') {
			steps {
				echo 'mvn --version'
				echo "Build Novo"
			}
		}
		stage('Test') {
			steps {
				echo "Test Novo"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test Novo"
			}
		} post {
			always {
				echo "I Run Always !"
			}
			success {
				echo "I Run OK !"
			}
			failure {
				echo "I Run when you fail"
			}
		}
	}
}