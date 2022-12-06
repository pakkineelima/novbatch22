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
                aws cloudformation create-stack --stack-name myteststack --parameters Parameterregion=us-east-2 --template-body file://createapache.yaml
             '''
  }
}
}
}
