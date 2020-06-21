pipeline {
	agent any
	tools {
        	maven 'MAVEN_HOME'
		jdk 'JDK_HOME'
	}
	stages {
		stage ('Build') {
      			steps {
          			bat 'mvn package'
      			}
    		}
  	}
}
