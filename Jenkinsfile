pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'composer install'
      }
    }
  }
  environment {
    HOME = '.'
  }
}