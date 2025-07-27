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

		environment {
			dockerHome = tool 'myDocker'
			mavenHome = tool 'myMaven'
			JAVA_HOME = tool 'JDK8'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
				// PATH = "/usr/local/bin:$PATH"
				// MAVEN_HOME = '/usr/share/maven'
				// NODE_HOME = '/usr/local/node'
				// JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
				// PATH = "$MAVEN_HOME/bin:$NODE_HOME/bin:$JAVA_HOME/bin:$PATH"
		}

		stages {
				stage('Checkout') {
						steps {
								sh 'mvn --version'
								sh 'docker version'
								echo "PATH - $PATH"
								echo "BUILD_NUMBER - $env.BUILD_NUMBER"
								echo "BUILD_ID - $env.BUILD_ID"
								echo "JOB_NAME - $env.JOB_NAME"
								echo "BUILD_TAG - $env.BUILD_TAG"
								echo "Building..."
						}
				}
				stage('Compile') {
						steps {
								echo "Compiling..."
								sh 'mvn clean compile'
						}
				}

				stage('Test') {
						steps {
								echo "Testing..."
								sh 'mvn test'
						}
				}

				stage('Integration Test') {
						steps {
								echo "Running integration tests..."
								sh 'mvn failsafe:integration-test failsafe:verify'
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