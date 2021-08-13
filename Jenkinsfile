pipeline {
   agent any
    stages {
	stage("Git checkout"){
	 steps{
	   git credentialsId: 'github-cred', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
	 }
	}
	stage("Java build stage"){
	 steps{
	  sh 'mvn clean package'
	 }
	}
	}
}
