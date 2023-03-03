pipeline {
	agent {	
		label 'pipeline-1'
		}
	stages {
		stage("SCM") {
			steps {
				git 'https://github.com/jitu9772/java-docker-app.git'
				}
			}

		stage("build") {
			steps {
				sh 'sudo mvn dependency:purge-local-repository'
				sh 'sudo mvn clean package'
				}
			}
		stage("Image") {
			steps {
				sh 'sudo docker build -t java-repo:$BUILD_TAG .'
				sh 'sudo docker tag java-repo:$BUILD_TAG jitu9772/pipeline-java:$BUILD_TAG'
				}
			}
				
	
		
		}
		
	}


