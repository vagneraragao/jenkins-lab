pipeline {
	stage('Build') {
		steps {
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
