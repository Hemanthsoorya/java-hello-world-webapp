pipeline {
   agent any
    stages {
	  stage("git checkout"){
	    steps{
		  git credentialsId: 'github-cred', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
		}
	  }
	  
	  stage("java build stage"){
	    steps{
		sh 'mvn clean package'
		}
	  }
	}
}
