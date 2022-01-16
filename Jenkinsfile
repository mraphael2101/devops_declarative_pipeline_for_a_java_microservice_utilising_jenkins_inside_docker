

// A DECLARATIVE PIPELINE

pipeline {
	
	// All subsequent steps will now happen inside a docker container
	agent { 
		label 'docker' 
		}
	
	stages {
		stage('Build') {
			steps {
				docker {
					label 'docker' 
					image 'maven:3.8.4'
					args '--name docker-node'
				}  
				// Example shell script in the groovy file
				sh 'mvn --version'
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
		always {
			echo "This block of code will always execute"
		}
		success {
			echo "This block of code only runs if the job is successful"
		}
		failure {
			echo "This block of code only runs if the job fails at a specific step"
		}
	}
}
