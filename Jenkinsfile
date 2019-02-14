pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''mysql --version

'''
        sh 'mysql -u root'
        sh 'mysql> CREATE DATABASE laravelJenkinsDb;'
        sh 'exit'
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