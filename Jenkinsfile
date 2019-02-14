pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''mysql --version
systemctl start mysql
'''
        sh '''mysql -u root
CREATE DATABASE demodb;
exit'''
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