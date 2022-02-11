pipeline {
   agent any
       stages{
           stage('Checkout') {
               steps {
                   git branch: 'main', credentialsId: 'GITHUBUPDATED', url: 'https://github.com/Nilakshi23/JobDetails.git'
                   
               }
           }
           stage('Details') {
               steps{
               script {
                   wrap([$class: 'BuildUser']) {
                       echo "JOB_NAME=${JOB_NAME}"
                       echo "BUILD_USER=${BUILD_USER}"
                       echo "BUILD_USER_ID=${BUILD_USER_ID}"
                       echo "BUILD_USER_EMAIL=${BUILD_USER_EMAIL}"
                       echo "BUILD_NUMBER=${BUILD_NUMBER}"
                  
                   }
               }
           }
           }
           stage('chatbot execution') {
               steps {
		   bat 'cd C:\\ProgramData\\Jenkins\\.jenkins\\workspace'
                   bat 'python chatbot.py %JOB_NAME% %BUILD_USER% %BUILD_NUMBER% %BUILD_USER_EMAIL%'
               }
           }
       }
}
