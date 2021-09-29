pipeline {
   agent any
    stages {
	  stage("git checkout"){
	    steps{
		  git credentialsId: 'github-cred', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
		}
	  }
	  
	  stage("maven build"){
	    steps{
		sh 'mvn clean package'
		}
	  }
	}
}
