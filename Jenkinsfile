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
        sh '''curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz
tar xzvf docker-17.04.0-ce.tgz 
mv docker/docker /usr/local/bin 
rm -r docker docker-17.04.0-ce.tgz
docker build -t "kokota/ktest" .
docker login -u kokota -p daixin123
docker push kokota/ktest'''
      }
    }

  }
}