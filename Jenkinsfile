pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'sudo /opt/lampp/lampp startmysql'
        sh 'composer install'
        sh 'cp .env.example .env'
        sh 'php artisan key:generate'
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