pipeline {
  agent {
    docker {
      image 'node:10-alpine'
      args '-p 8081:8081'
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
        sh './test.sh'
      }
    }

    stage('Deliver') {
      steps {
        input 'Continue or Exit?'
        sh 'echo \'deliver\''
      }
    }

  }
}