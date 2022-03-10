pipeline {
agent any
 stages{
 stage("Git checkout"){
 steps{
 git credentialsId: 'Github-cer', url: 'https://github.com/Hemanthsoorya/java-hello-world-webapp.git'
 }
 }
 stage("maven built"){
 steps{
 sh 'mvn clean package'
 sh "mv target/*.war target/myweb.war"
 }
 }
 stage("War File Deploy"){
 steps{
 sshagent(['Slave id']) {
    // some block
sh "scp -o StrictHostKeyChecking=no target/myweb.war Ubuntu@3.111.39.119:/var/lib/tomcat8/webapps"
}
 }
 }
 }
 }



