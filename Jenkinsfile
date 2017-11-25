pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deliver') {
      steps {
        sh '''echo \'a\'
input message: \'Finished? (Click "Proceed" to continue)\'
'''
      }
    }
  }
  environment {
    CI = 'true'
  }
}