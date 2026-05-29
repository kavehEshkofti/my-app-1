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
                    sh "${mvnHome}/bin/mvn clean package"
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
