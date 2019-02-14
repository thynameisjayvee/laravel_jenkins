pipeline {
  agent {
    docker {
      image 'php'
    }

  }
  stages {
    stage('error') {
      steps {
        sh '''php --version
composer install --prefer-dist'''
      }
    }
  }
}