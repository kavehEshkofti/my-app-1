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
            def mvnHome = tool name: 'maven-3', type: 'maven'
            steps {
                sh "${mvnHome}/bin/mvn package"
            }
        }
        
    }

}
