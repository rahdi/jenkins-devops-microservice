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
}