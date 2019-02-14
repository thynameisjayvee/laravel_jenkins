pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'composer install'
        sh 'php artisan key:generate'
      }
    }
  }
  environment {
    HOME = '.'
  }
}