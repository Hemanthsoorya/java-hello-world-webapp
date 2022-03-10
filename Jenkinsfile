pipeline {
agent any
 stages{
 stage("Git checkout"){
 steps{
 git credentialsId: 'Github-cer', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
 }
 }
 stage("java build"){
 steps{
 sh 'mvn clean package'
 }
 }
  stage("War File Deploy"){
 steps{
 sshagent(['slave-id']) {
    // some block
sh "scp -o StrictHostKeyChecking =no target/myweb.war Ubuntu@3.111.39.119:/var/lib/tomcat8/webapps"
}
 }
 }
}
}
