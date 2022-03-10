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
 }
}
