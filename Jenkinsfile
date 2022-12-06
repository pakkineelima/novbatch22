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
    } 
     stage("Run cloudformaiton stack") {
        steps{  
           withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: '	awscredentials', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY']]) {
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml
             '''
    }
  }
}
}
        
    

