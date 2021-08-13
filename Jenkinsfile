pipeline {
   agent any
    stages {
	stage("Git checkout"){
	 steps{
	   git credentialsId: 'github-cred', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
	 }
	}
	stage("Maven build"){
	 steps{
	  sh 'mvn clean package'
	 }
	}
	}
}
