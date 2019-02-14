pipeline {
  agent {
    docker {
      image 'php'
      args '-u 0'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''php --version
php -r "copy(\'https://getcomposer.org/installer\', \'composer-setup.php\');"
php -r "if (hash_file(\'sha384\', \'composer-setup.php\') === \'48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5\') { echo \'Installer verified\'; } else { echo \'Installer corrupt\'; unlink(\'composer-setup.php\'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink(\'composer-setup.php\');"
'''
        sh 'apt-get install --yes zip unzip php-pclzip'
      }
    }
    stage('Install') {
      steps {
        sh '''php composer.phar install
'''
        sh 'php artisan key:generate'
      }
    }
  }
  environment {
    HOME = '.'
  }
}