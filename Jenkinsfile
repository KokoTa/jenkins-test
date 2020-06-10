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
        sh '''docker build -t "kokota/ktest" .
docker login -u kokota -p daixin123
docker push kokota/ktest'''
      }
    }

  }
}