// Scripted syntax
// node {	
// 		echo "Build"	
// 		echo "Test"	
// 		echo "Integration Test"
// }

// Declarative syntax
pipeline {
		agent any

		stages {
				stage('Build') {
						steps {
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