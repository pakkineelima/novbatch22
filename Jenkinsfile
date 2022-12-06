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
           withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: '285562202312', usernameVariable: 'AKIAUE7GVNDELMG62E4N', passwordVariable: 'oV/93+nl64ozTCpupcMRmO6tFw6luOyOPAqLWJBD']]) {
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml
             '''
    }
  }
}
}
}
