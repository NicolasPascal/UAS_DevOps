pipeline {
  agent {
    docker {
      image 'docker:24.0.2'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    }
  }
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
