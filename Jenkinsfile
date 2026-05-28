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
                sh 'mvn package'
            }
        }
        
    }

}
