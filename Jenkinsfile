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
        			//withCredentials([usernamePassword(credentialsId: '2bd6a395-dbe2-4a03-a15f-52fd9241d806', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
				bat 'cf login -a https://api.run.pivotal.io -u rihab.ayachi@etudiant-enit.utm.tn -p 123456Seven* -o rihab.ayachi'
          			bat 'cf push'
				}
    			}
    		}
  	}
}
