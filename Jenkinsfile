pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
        echo 'Build complete'
      }
    }

    stage('Test') {
      steps {
        sh '''mvn clean verify sonar:sonar 






-Dsonar.projectKey=devops -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqb_edf5bc86981026ab42945e0d2f62c7226440fede'''
      }
    }

  }
}