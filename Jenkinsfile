#!groovy
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3'))])

node {
   /* 
    stage('Checkout') { 
   git branch: 'master', credentialsId: '21311c83-a7a7-4316-8a19-b5b828aaf1a9', url: ' https://github.com/MithunTechnologiesDevOps/maven-web-application.git'

   }
 */
 
 stage('Checkout'){

     checkout scm
  }
  
   stage('Testing')
   {
    if(isUnix()){
     sh 'mvn test'
      }
      else{
       bat 'mvn test'   
      }
   }
   /*
   stage('SonarQube Report Generation')
   {
    if(isUnix()){
     sh 'mvn sonar:sonar'
      }
      else{
       bat 'mvn sonar:sonar'   
      }
   }
    
    stage('NexusDeploy')
   {
    if(isUnix()){
     sh 'mvn deploy'
      }
      else{
       bat 'mvn deploy'   
      }
   }
   
   stage ('Deploy to Tomcat'){
       
       sh 'echo deploying application into tomcat'
       sh 'cp $WORKSPACE/target/*.war /Users/bhaskarreddyl/BhaskarReddyL/Softwares/Running/apache-tomcat-9.0.12/webapps/'
       sh 'echo deploymnet done'
   }
   */
   stage ('Email Notifcation'){
       
       mail bcc: '', body: '''Build done

Regards,
Satyabrata Mishra''', cc: 'satya.m@gmail.com', from: '', replyTo: '', subject: 'Deployment Completed', to: 'devtest@gmail.com,test.inbox@gmail.com'
   } 
    
}
