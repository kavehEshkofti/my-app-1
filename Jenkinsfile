node{
    stage('SCM Checkout'){
      git 'https://github.com/kavehEshkofti/my-app-1.git'
    }
    stage('Compile-Package'){
      sh 'mvn package'
    }
}
