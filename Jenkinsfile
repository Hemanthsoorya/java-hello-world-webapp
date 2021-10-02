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
		    sh 'mv target/*.war target/myweb.war'
		}
	  }
	    stage("war file deploy"){
	    steps{
	     sshagent(['slave-id']) {
	     sh "scp -o StrictHostKeyChecking=no ta=norget/myweb.war ubuntu@172.31.7.174:/var/lib/tomcat8/webapps"
		}
	   }
	 }
     }
}
