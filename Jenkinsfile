pipeline {
	agent {
		docker{
			image 'maven:3.6.0'
			}
	}
  options {
    timestamps()
  }
	stages {
	 stage('Build') {
	 	steps {
	 	  sh "mvn install"
	 		}
	 	}
	 stage('Test') {
	 	steps {
	 	  sh "mvn test"
	 		}
		}
	}
	post{
		success{
		archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
		}
	}
}
