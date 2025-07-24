pipeline {
  agent any
  stages {
    stage('Build Image') {
      steps {
        sh 'docker build -t inventory-app:latest .'
      }
    }
    stage('Unit Test') {
      steps {
        sh 'pytest tests/'
      }
    }
  }
}
