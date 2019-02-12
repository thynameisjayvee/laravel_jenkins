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
sudo apt-get install git
composer install --prefer-dist'''
      }
    }
  }
}