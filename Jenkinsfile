pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/kavehEshkofti/my-app-1.git'
            }
        }
        
        stage('Build with Maven') {            
            steps {
               script {
                    def mvnHome = tool name: 'maven-3', type: 'maven'
                    sh "${mvnHome}/bin/mvn package"
                }
            }
        }

       stage('SonarQube Analysis') {
          steps{
              script{
                 def mvnHome =  tool name: 'maven-3', type: 'maven'
                 withSonarQubeEnv('sonar-server') { 
                   sh "${mvnHome}/bin/mvn sonar:sonar"
                 }
              }
          }
       }

       stage('Email'){
            steps{
                script{
                    mail bcc: '', body: 'Hello world', cc: '', from: '', replyTo: '', subject: 'job', to: 'kaveh_eshkofti@yahoo.com'
                }
            }
        }
        
    }

}
