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
    } stage('Run scripts') {
       steps {
        script {
          with credentials([[
            $class: 'AmazonWebServicesCredentialsBinding',
            accessKeyVariable: 'AKIAUE7GVNDEOK2LLBTW'
            secretKeyVariable: '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',
            credentialsId: '9369d669-390c-4526-b8f6-ea8ba4557a64'
          ]])
        }
       }
    }
      stage('Run cloudformaiton stack') {
        steps{  
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml
              '''
  }
}
}
