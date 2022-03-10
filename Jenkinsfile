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
 sshagent(['slave-id2']) {
    // some block
sh "scp -o StrictHostKeyChecking=no target/myweb.war Ubuntu@172.31.9.165:/var/lib/tomcat8/webapps"
}
 }
 }
 }
 }



