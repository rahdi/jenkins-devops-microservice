// Scripted syntax
// node {	
// 		echo "Build"	
// 		echo "Test"	
// 		echo "Integration Test"
// }

// Declarative syntax
pipeline {
		agent any

		// agent {
		// 	docker {
		// 		image 'maven:3.6.3-jdk-11'
		// 	}
		// }

		// agent {
		// 	docker {
		// 		image 'node:14.17.0'
		// 	}
		// }

		stages {
				stage('Build') {
						steps {
								// sh 'mvn --version'
								// sh 'node --version'
								echo 'PATH - $PATH'
								echo 'BUILD_NUMBER - $env.BUILD_NUMBER'
								echo 'BUILD_ID - $env.BUILD_ID'
								echo 'JOB_NAME - $env.JOB_NAME'
								echo 'BUILD_TAG - $env.BUILD_TAG'
								echo 'Building...'
						}
				}
				stage('Test') {
						steps {
								echo 'Testing...'
						}
				}
				stage('Integration Test') {
						steps {
								echo 'Running integration tests...'
						}
				}
		} 
		
		post {
			always {
				echo 'This will always run after the stages complete.'
			}

			success {
				echo 'This will run only if the pipeline succeeds.'
			}

			failure {
				echo 'This will run only if the pipeline fails.'
			}
		}
}