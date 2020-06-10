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
		stage ('Deploy') {
			steps {
        			withCredentials([usernamePassword(credentialsId: 'CF_Credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
					bat 'cf login -a https://api.run.pivotal.io -u ${USERNAME} -p ${PASSWORD} -o rihab.ayachi'
          			bat 'cf push'
				}
    			}
    		}
  	}
}
