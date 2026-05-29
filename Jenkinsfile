node{
   stage('SCM Checkout'){
     git 'https://github.com/kavehEshkofti/my-app-1'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   
   stage('SonarQube Analysis') {
        def mvnHome =  tool name: 'maven-3', type: 'maven'
        withSonarQubeEnv('sonar-server') { 
          sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }
   
   stage('Email Notification'){
      mail bcc: '', body: 'Hello world', cc: '', from: '', replyTo: '', subject: 'job', to: 'kaveh_eshkofti@yahoo.com'
   }
}
