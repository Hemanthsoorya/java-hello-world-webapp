pipeline {
   agent any
    stages {
	stage("Git checkout"){
	 steps{
	   git credentialsId: 'github-cred', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
	 }
	}
		stage("Build stage"){
	 steps{
	  sh 'mvn clean package'
	  sh "mv target/*.war target/myweb.war"
	 }
	}
	stage("war file deploy"){
	 steps{
	  sshagent(['slave-id']) {
	   sh "scp-o StrictHostKeyChecking=no target/myweb.war ubuntu@172.31.5.254:/var/lib/tomcat8/webapps"
	}
	 }
	  }
	}
}
