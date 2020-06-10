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
        			withCredentials([$class: 'VaultUsernamePasswordCredentialBinding'(
        					credentialsId   : '2bd6a395-dbe2-4a03-a15f-52fd9241d806',
                        			usernameVariable: 'USERNAME',
                                      		passwordVariable: 'PASSWORD')]) {
					bat 'cf login -a https://api.run.pivotal.io -u $USERNAME -p $PASSWORD -o rihab.ayachi'
          				bat 'cf push'
				}
    			}
    		}
  	}
}
