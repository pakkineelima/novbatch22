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
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml --region us-east-2 --aws_access_key_id AKIAUE7GVNDEOK2LLBTW --aws_secret_access_key 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 
              '''
  }
}
}
}
