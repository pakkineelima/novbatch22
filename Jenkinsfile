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
             withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: '6639ebb7-65b8-46eb-8107-2aeb4b262d61', usernameVariable: 'jenkins_user', passwordVariable: 'pWotXArjvW9}9+v']]) {
             sh '''
                aws cloudformation create-stack --stack-name myteststack --template-body createapache.yaml --region us-east-2 
              '''
  }
}
}
}
}
