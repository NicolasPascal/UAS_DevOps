pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/NicolasPascal/UAS_DevOps.git'
      }
    }
    stage('Build Image') {
      steps {
        sh 'docker build -t inventory-app:latest .'
      }
    }
    stage('Unit Test') {
      steps {
        sh 'pytest tests/'  // atau 'mvn test'
      }
    }
    stage('Code Scan') {
      steps {
        withSonarQubeEnv('My SonarQube') {
          sh 'sonar-scanner'
        }
      }
    }
    stage('Deploy to K8s') {
      steps {
        sh 'kubectl apply -f k8s/deployment.yaml'
      }
    }
  }
}
