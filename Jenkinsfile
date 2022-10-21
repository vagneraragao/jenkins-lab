pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } } 
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh "docker version"
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "Nova Entrega Continua"
			}
		}
		stage('Compile') {
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
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker Image') {
			steps {
				script {
					//dockerImage = docker.build("vmaragao/currency-exchange-devops:${env.BUILD_TAG}")
					dockerImage = docker.build("vmaragao/currency-exchange-devops:22")
				}
			}
		}
		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('','dockerhub') {
						dockerImage.push();
						dockerImage.push('latest');
					}
				}
			}
		}
	}
}