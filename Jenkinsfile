pipeline {
   agent any
    stages {
	  stage("Git checkout"){
	    steps{
		 git credentialsId: 'Github-cer', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'	
		 }
	  } 
	  stage("Build Stage"){
	    steps{
		sh 'mvn clean package'
		sh 'mv target/*.war target/webapp.war'
		}
	  }
	  stage("war file deploy"){
          steps{
          sshagent(['slave-id']) {
	  sh "scp -o StrictHostKeyChecking=no target/webapp.war ubuntu@172.31.37.128:/var/lib/tomcat8/webapps"
		}
		}
	  }
     }
}
