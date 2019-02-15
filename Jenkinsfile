pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''cd docker
git --version
'''
        sh '''mysql --version

'''
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