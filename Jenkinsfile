pipeline {
    agent any
    stages{
      stage('Checkout external proj') {
        steps {
            git branch: 'main',
                credentialsId: '984299d6802457efd37c7bbfab51de45',
                
                url: 'https://github.com/pakkineelima/novbatch22.git'

            sh "ls -lat"
        }
    }
      stage('Run cloudformaiton stack') {
        steps{  
           withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 9369d669-390c-4526-b8f6-ea8ba4557a64', usernameVariable: 'iamuser', passwordVariable: '4N1L&Ff]!MUoR-D']]) {
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml
             '''
    }
  }
}
}
}
