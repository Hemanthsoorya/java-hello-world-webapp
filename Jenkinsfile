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
		sh 'mv target/*.war target/Surya.war'
		}
	  }
	  stage("war file deploy"){
          steps{
          sshagent(['slave-ID']){
	  sh "scp -o StrictHostKeyChecking=no target/Surya.war ubuntu@65.0.125.16:/var/lib/tomcat8/webapps"
		}
		}
	  }
     }
}
