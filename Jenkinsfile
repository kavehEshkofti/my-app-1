node{
    stage('SCM Checkout'){
      steps {
                git branch: 'main', 
                    url: 'https://github.com/kavehEshkofti/my-app-1.git'
            }
    }
    stage('Compile-Package'){
      sh 'mvn package'
    }
}
