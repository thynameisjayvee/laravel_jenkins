pipeline {
  agent {
    docker {
      image 'node'
    }

  }
  stages {
    stage('error') {
      steps {
        sh 'npm install'
      }
    }
  }
  environment {
    HOME = '.'
  }
}