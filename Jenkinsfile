pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('Build') {
      steps {
        cleanWs(cleanWhenFailure: true, cleanWhenAborted: true)
      }
    }

  }
}