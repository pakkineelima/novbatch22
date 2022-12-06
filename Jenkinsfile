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
             withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: '76754c97-e3c2-4420-80f7-d49be03e5209', usernameVariable: 'AKIAUE7GVNDELWA5XRPH', passwordVariable: '9RYYOvhfvWJ8mIplFOlpHu/9LqCyc/MBSbSqV+cd']]) {
              sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml --region us-east-2 
              '''
             }
  }
}
}
}
