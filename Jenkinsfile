node
{
    def mavenHome = tool name: "maven3.8.5"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])    
    
   echo "The jon name is:" ${env.JOB_NAME}"
echo "The node name is: ${env.NODE_NAME}"
echo "The workspace path is: {env.WORDSPACE}"
echo "the node lable is : ${env.NODE_Labels}" 
echo "the buils number is: ${env.BUILD_NUMBER}"
 
    
stage('CheckoutCode'){
git branch: 'development', credentialsId: '3cf27e7d-8f06-447d-bb67-785c157a3c29', 
url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
}
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"  
}
       /*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage ( 'DeployAppIntoTomcatServer'){
sshagent(['45c9165b-5a59-47d5-b35e-20b19ca6788e']) {
 sh "scp target/maven-web-application.war ec2-user@65.2.148.17:/opt/apache-tomcat-9.0.64/webapps/"   
}
}

*/
}

