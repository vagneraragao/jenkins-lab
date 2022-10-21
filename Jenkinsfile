pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } } 
	stages {
		stage('Build') {
			steps {
				// sh 'mvn --version'
				// echo "Build Novo"
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test') {
			steps {
				echo "Teste Novo"
			}
		}
	}
}