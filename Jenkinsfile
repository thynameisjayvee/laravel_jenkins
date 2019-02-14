pipeline {
  agent {
    docker {
      image 'mysql'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''mysql --version

'''
        sh '''systemctl start mysql
mysql -u root --init-command=\'CREATE DATABASE laravelJenkinsDb;\''''
        sh 'composer install'
        sh 'cp .env.example .env'
        sh 'php artisan key:generate'
        sh '''php artisan make:auth
php artisan migrate'''
      }
    }
    stage('Node') {
      steps {
        sh 'npm install'
        sh 'npm run dev'
      }
    }
  }
  environment {
    HOME = '.'
  }
}