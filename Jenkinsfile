pipeline {
  agent {
    docker {
      image 'php'
    }

  }
  stages {
    stage('error') {
      steps {
        sh '''echo "hello"
composer install'''
      }
    }
  }
}